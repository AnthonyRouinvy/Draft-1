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

> > error: src refspec master does not match any.
 
Relancer la configuration et voir si l'étape du Git passe

`node wiki configure`

Il y a un petit décalage entre le moment où l'on créé un article et celui où il est poussé. On peut voir sur Gitkraken que les fichiers sont en premier poussés en staging, puis après commités.

### Démarrer / arrêter

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



Repository url
https://github.com/AnthonyRouinvy/wiki.git
Authentication choisir `Basic` avec mes identifiants Github
Cocher commit using user email

