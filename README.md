Pour installer PHP et démarrer un serveur sous Ubuntu, consultez le [wiki](https://github.com/Varkoff/wcs-ubuntu-install/wiki#installer-php-72) !

# Installation du thème "starship"
![](https://raw.githubusercontent.com/starship/starship/master/media/demo.gif)
[Consultez le wiki](https://github.com/Varkoff/wcs-ubuntu-install/wiki/Installer-le-th%C3%A8me-Starship-%C3%A0-votre-invit%C3%A9-de-commande)

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
