<!-- TITLE: Flask -->
<!-- SUBTITLE: A quick summary of Flask -->

# Python Flask
Général documentation.

## Virtual env
Il est important d'utiliser une **virtual env**, soit de le définir via l'IDE PyCharm ou depuis le Terminal pour le projet. C'est lui qui permettra d'utiliser `pip` pour installer des packages.

## Terminal
**Lancer l'application**
Démarrer une application depuis le Terminal permet de relancer le navigateur et voir les changements.

```sh
FLASK_APP=flask_mysql.py FLASK_DEBUG=1 python -m flask run --port=8082
```

**Installer des packages**
L'installation de packages passe par pip, ne pas oublier de rajouter le package dans requirements.txt

```sh
pip install Flask-SQLAlchemy
```


Exempe de fichier requirements.txt

```sh
Flask
Flask-Admin
Flask-SQLAlchemy
Flask-Security>=1.7.5
```

Pour installer les packages du fichier `requirements.txt`


```sh
pip install -r requirements.txt 
```

Pour savoir si un package est installé


```sh
pip show package
```


Rechercher un package


```sh
pip search package
```

## Issue

### Flask-MySQLDB

L'installation pose problème, voici les étapes dans le terminal. Ne pas oublier d'ajouter les pip dans `requirements.txt`.


```sh
 sudo apt-get install python3-mysqldb 
 sudo apt-get install python3-dev
 pip install mysql
 pip install mysqlclient
 pip install flask-mysqldb
 pip show flask-mysqldb
```

 
 



