# Installation d'un virtual host sur apache sous debian

## 1. Créer le fichier conf

les fichiers de configuration des virtual hosts d'apache se trouvent dans le dossier

    /etc/apache2/site-availables/

Pour créer un fichier de conf, on peut copier le fichier de conf par défaut :

    cp /etc/apache2/site-avalaibles/000-default.conf /etc/apache2/site-availables/example.conf

## 2. Créer la configuration
En éditant le fichier `example.conf` on observe ceci :

    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html
    
Nous allons modifier ces champs et en ajouter d'autres :

    ServerAdmin webmaster@localhost
    ServerName example.monDomaine.com
    DocumentRoot /var/www/html/example_directory
    
On précise donc dans ServerName l'adresse complète par laquelle on veut accéder à ce site

On précise également dans DocumentRoot quel dossier doit être "visé" par cette adresse

## 3. Activer le virtual host

Pour activer le virtual host, il faut utiliser la commande `a2ensite` pour APACHE2 ENABLE SITE :

    a2ensite example.conf
    
Enfin, il suffit de redémarrer le service apache pour prendre en compte cette nouvelle configuration

    service apache2 restart
    
Et c'est prêt !