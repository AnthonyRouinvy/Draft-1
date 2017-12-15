<!-- TITLE: Apache 2 -->
<!-- SUBTITLE: A quick summary of Apache 2 -->

# Apache2

## Procédure pour ajouter un serveur

**Apache2**

```sh
cd /etc/apache2/sites-available
vim wikidocs.com.conf
cd ../sites-enabled
ln -s ../sites-available/wikidocs.com.conf .
apache2ctl graceful
```


**Hosts**

```sh
sudo vim /etc/hosts
127.0.0.1       wikidocs.com www.wikidocs.com
```


## Configuration VirtualBox et Windows

**Windows**
NotePad++ C:\Windows\System32\drivers\etc\hosts

```sh
127.0.0.1 wikidocs.com www.wikidocs.com
```


**VirtuaBox**
Clic droit sur la machine virtuelle, Configuration, Réseau, Avancé, Redirection de ports

```sh
Nom: UbuntuMate
Protocole: TCP
IP hôte: 127.0.0.1
Port hôte: 80
IP invité: 10.0.2.15
Port invité: 80
```

## Mes conf

Voici le contenu pour mes fichiers Apache2 de sites-available


```sh
$ cd /etc/apache2/sites-available
$ ls -1
000-default.conf
conceptqai.com.conf
default-ssl.conf
proj-flask1.com.conf
wikidocs.com.conf
```

**Contenu de conceptqai.com.conf**

```apache_conf
<VirtualHost *:80>
    ServerAdmin no-reply@conceptqai.com
    ServerName conceptqai.com
    ServerAlias www.conceptqai.com
    
    ProxyPreserveHost On

     ProxyPass / http://127.0.0.1:8081/
     ProxyPassReverse / http://127.0.0.1:8081/  

    ErrorLog /var/log/apache2/error-conceptqai.com.log

    # Possible values include: debug, info, notice, warn, error, crit,
    # alert, emerg.
    LogLevel warn

    CustomLog /var/log/apache2/access-conceptqai.com.log combined

</VirtualHost>
```

**Contenu de proj-flask1.com**

```apache_conf
<VirtualHost *:80>
    ServerAdmin no-reply@proj-flask1.com
    ServerName proj-flask1.com
    ServerAlias www.proj-flask1.com
    
    ProxyPreserveHost On

     ProxyPass / http://127.0.0.1:8082/
     ProxyPassReverse / http://127.0.0.1:8082/  

    ErrorLog /var/log/apache2/error-proj-flask1.com.log

    # Possible values include: debug, info, notice, warn, error, crit,
    # alert, emerg.
    LogLevel warn

    CustomLog /var/log/apache2/access-proj-flask1.com.log combined

</VirtualHost>
```

**Contenu de  wikidocs.com.conf**


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

**Contenu de la page défaut Apache 000-default.conf**


```sh
<VirtualHost *:80>
	ServerAdmin webmaster@localhost
	DocumentRoot /var/www/html
  ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```


	
	