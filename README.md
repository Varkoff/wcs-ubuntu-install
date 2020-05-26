Pour installer PHP et démarrer un serveur sous Ubuntu, consultez le [wiki](https://github.com/Varkoff/wcs-ubuntu-install/wiki#installer-php-72) !

# Installation du thème "starship"
![](https://raw.githubusercontent.com/starship/starship/master/media/demo.gif)
[Consultez le wiki](https://github.com/Varkoff/wcs-ubuntu-install/wiki/Installer-le-th%C3%A8me-Starship-%C3%A0-votre-invit%C3%A9-de-commande)

# Installer Mysql
1. Lancer la commande `sudo mysql_secure_installation utility`
2. Suivez les instructions du terminal
3. Sur certaines versions comme la 18.04, je n'arrivais pas à me connecter avec la commande `mysql -u root -p`
4. J'ai du recréer un utilisateur et lui donner les privilèges d'administration
- Se connecter avec mysql `sudo mysql`
- Créez votre compte utilisateur `CREATE USER 'USERNAME'@'localhost' IDENTIFIED BY 'PASSWORD';`
- Donnez lui les permissions à toutes les bases `GRANT ALL PRIVILEGES ON *.* TO 'USERNAME'@'localhost'`
- Où seulement les permissions à une seule base `GRANT ALL PRIVILEGES ON DB_NAME.* TO 'USERNAME'@'localhost'`
5. Effectuer un `mysql -u USERNAME -p` devrait fonctionner

# Créer un utilisateur Sudo
1. `adduser USERNAME`
2. `sudo usermod -aG sudo username`
3. Vérifier que ça a fonctionné avec `su - username`

# Changer les permissions d'un utilisateur sur des fichiers
1. `sudo chown -R USERNAME path/to/dir/`
2. `sudo chmod -R 777 USERNAME path/to/dir/`

# Lancer Apache2 et retirer la page par défaut
1. Créer un nouveau fichier config pour apache en copiant celui par défaut : 
> `sudo cp /etc/apache2/sites-available/000-default.config /etc/apache2/sites-available/DOMAIN.config`
> `sudo cp /etc/apache2/sites-available/default-ssl.config /etc/apache2/sites-available/DOMAIN-ssl.config`
> `sudo a2ensite DOMAIN.config`
> `sudo ae2dissite DOMAIN`
> `sudo systemctl reload apache2 && sudo systemctl restart apache2`

# Installer Certbot pour les certificats SSL
1. https://certbot.eff.org/lets-encrypt/ubuntubionic-apache
