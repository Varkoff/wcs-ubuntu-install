Ayant réinstallé Ubuntu plusieurs fois durant la formation, j'ai décidé de lister la plupart des dépendances et des librairies.

__Voici ci-dessous la marche à suivre__

# Installer les dépendances PHP
1. `sudo apt update && sudo apt upgrade'`
2. `sudo apt install php php-xml php-cgi php-cli php-curl curl wget mysql-server composer git php-mysql`
3. `sudo apt full-upgrade && sudo apt autoremove`
4. Installer phpstorm, googlechrome, visualstudiocode, discord, slack ...
# Pour lancer un hébergement web, il faut également installer
5. `sudo apt install apache2 php libapache2-mod-php mysql-server php-mysql`
6. `sudo apt install php-curl php-gd php-intl php-json php-mbstring php-xml php-zip`

# Installer le thème "starship"
![](https://raw.githubusercontent.com/starship/starship/master/media/demo.gif)
1. sudo apt install zsh
2. Lancer ZSH avec la commande `zsh`
3. Appuyer sur `2` pour les paramètres par défaut de zsh
4. Ecrire `chsh` pour mettre zsh en paramètre par défaut
5. Redémarrer Ubuntu
6. Télécharger les polices du terminal avec `sudo apt-get install fonts-powerline`
7. Télécharger le thème avec `curl -fsSL https://starship.rs/install.sh | bash`
8. Ouvrir le fichier de config de ZSH `~./.zshrc` avec la commande `sudo gedit ~/.zshrc`
9. Ajouter les lignes `eval "$(starship init bash)"` à la fin du fichier
10. Enregistrer
11. Relancer le terminal

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