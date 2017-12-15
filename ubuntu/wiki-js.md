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


### Download & configure

```sh
mkdir Wikidocs
cd Wikidocs
sudo curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo chown -R anthonyr: .
node wiki configure
```
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