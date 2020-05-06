Ayant réinstallé Ubuntu plusieurs fois durant la formation, j'ai décidé de lister la plupart des dépendances et des librairies.

__Voici ci-dessous la marche à suivre__

# Installer les dépendances PHP
1. `sudo apt install php php-xml php-cgi php-cli php-curl curl wget mysql-server composer git php-mysql`
2. `sudo apt full-upgrade && apt autoremove`
3. Installer phpstorm, googlechrome, visualstudiocode, discord, slack ...

# Installer le thème "starship"
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
- Créez votre compte utilisateur `CREATE USER 'VOTRE_NOM'@'localhost' IDENTIFIED BY 'VOTRE_MOT_DE_PASSE';`
- Donnez lui les permissions `GRANT ALL PRIVILEGES ON *.* TO 'VOTRE_NOM'@'localhost' IDENTIFIED BY 'VOTRE_MOT_DE_PASSE'`
5. Effectuer un `mysql -u VOTRE_NOM -p` devrait fonctionner# wcs-ubuntu-install
