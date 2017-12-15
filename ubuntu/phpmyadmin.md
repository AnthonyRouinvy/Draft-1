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

  
# Issues


## Access denied

Message d'erreur dans PHPMyAdmin au bas de la page, cela n'empêche pas de voir les tables.

> mysqli_real_connect(): (HY000/1045): Access denied for user 'phpmyadmin'@'localhost' (using password: YES)

Changer dbuser "phpmyadmin" par "root", pas besoin de redémarrer.


```sh
vim /etc/phpmyadmin/config-db.php
```




