<!-- TITLE: Phpmyadmin -->
<!-- SUBTITLE: A quick summary of Phpmyadmin -->

# PHPMyAdmin
> Important: durant l'installation, faire attention de bien cocher Apache2 en serveur


```sh
sudo apache2ctl stop
sudo apt-cache search phpmyadmin
sudo apt-get install mysql-server
apt-get install phpmyadmin
apache2ctl start
```

Pour y accéder http://localhost/phpmyadmin
Si une erreur se produit, on peut reconfigurer


```sh
dpkg-reconfigure phpmyadmin
```
