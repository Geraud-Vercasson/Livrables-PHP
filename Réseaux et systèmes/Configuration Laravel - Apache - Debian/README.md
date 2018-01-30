# Configuration Laravel - Apache - Debian

1. Créer / cloner le projet Laravel dans un répertoire utilisable par Apache. (ex `/var/www/monProjet`)

2. Créer un virtual host pointant sur le dossier public dans mon projet, avec les options suivantes :

        <VirtualHost *:80>
          ServerName monProjet.monSite.com
          DocumentRoot "/var/www/monProjet/public"
          <Directory "/var/www/monProjet/public">
            AllowOverride all
          </Directory>
        </VirtualHost>

3. Finaliser le virtual host

        a2ensite monProjet.conf
        service apache2 restart

4. Donner à Apache les droits nécessaires :

        chown -R www-data:www-data /var/www/monProjet/storage

Et voilà!