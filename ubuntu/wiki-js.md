<!-- TITLE: Wiki Js -->
<!-- SUBTITLE: A quick summary of Wiki Js -->

# WikiJS
## Install
L'installation ne s'est pas fait sans problème, il est conseillé de lire leur documentation et bien faire attention aux conseils.

### Pre-required

```sh
sudo apt-get install yarn
sudo apt-get install mongodb
sudo apt-get install nodejs
```


### Download

```sh
mkdir Wikidocs
cd Wikidocs
sudo curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo chown -R anthonyr: .
node wiki configure
```

### Configure Git
Si la configuration de Git n'est pas passée, suivre ces étapes.

**Configuration Git**
Se connecter sur Github et créer un Repo
 

```sh
cd repo
rm -rf .git
git init
git add home.md
git commit -m "first commit"
git remote add origin https://github.com/AnthonyRouinvy/wikidocs.git
git push -u origin master
```
Si on ne pousse pas un fichier dans le master, on aura l'erreur

> error: src refspec master does not match any.
 
Relancer la configuration et voir si l'étape du Git passe

`node wiki configure`

> Repository url
> https://github.com/AnthonyRouinvy/wiki.git
> Authentication choisir `Basic` avec mes identifiants Github
> Cocher commit using user email


Il y a un petit décalage entre le moment où l'on créé un article et celui où il est poussé. On peut voir sur Gitkraken que les fichiers sont en premier poussés en staging, puis après commités.

### Configurer Apache2

Etapes à suivre pour la configuration d'Apache sans quoi le site s'affichera sans charger les JS/CSS.

```
cd /etc/apache2/sites-available
vim wikidocs.com.conf
```


```apache_conf
 <VirtualHost *:80>
    ServerAdmin arouinvy@docs.wiki
    ServerName wikidocs.com
    ServerAlias www.wikidocs.com
    ProxyPreserveHost On

    # setup the proxy
    <Proxy *>
        Order allow,deny
        Allow from all
    </Proxy>
    ProxyPass / http://localhost:8084/
    ProxyPassReverse / http://localhost:8084/
</VirtualHost>
```

```
cd ../sites-enabled
ln -s ../sites-available/wikidocs.com.conf .
apache2ctl graceful
```

### Configurer hosts

**Sur Ubuntu**

```sh
sudo vim /etc/hosts
127.0.0.1       wikidocs.com www.wikidocs.com
```

**Sur Windows**

```sh
NotePad++ C:\Windows\System32\drivers\etc\hosts
127.0.0.1 wikidocs.com www.wikidocs.com
```

### Démarrer / arrêter

Se déplacer dans le répertoire de Wikidocs

```sh
node wiki start
node wiki stop
```
 **Créer un lanceur dans la barre de menu**
 Clic droit sur le menu
 Ajouter au tableau de bord
 Lanceur personnalisé
 Commande: sh /home/anthonyr/Wikidocs/launch.sh

 `vim launch.sh`
 
```sh
#!/bin/bash
 cd /home/anthonyr/Wikidocs
 node wiki start
```
 
` chmod +x launch.sh`


### Changement de domaine

Si on souhaite changer le nom du domaine, il faudra refaire les étapes et modifier le fichier du répertoire Wikidocs

```sh
vim config.yml
host: 'http://wikidocs.com'
port: 8084
```


Pour info, dans la partie Git j'avais ajouté, mais cela n'a pas servi

```yaml
git:
  url: 'https://github.com/AnthonyRouinvy/wikidocs.git'
  branch: master
  auth:
    type: basic
    username: arouinvy@gmail.com
    password: FDjksdDjhzmex9TJa2sm
    privateKey: ''
    sslVerify: true
  showUserEmail: true
  serverEmail: arouinvy@gmail.com
```





