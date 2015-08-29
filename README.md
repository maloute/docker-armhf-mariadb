# docker-armhf-mariadb
Image de base de Tumtum  (https://github.com/tutumcloud/mariadb) modifié pour l'odroid u3 et pour initialiser la config mysql 

# Installation 
## Construction de l'image 
```
docker build -t maloute/mariadb .
```
## Lancement de l'image
```
docker run --name=mariadb -v /srv/docker/mariadb/mysql:/var/lib/mysql -v /srv/docker/mariadb/my.cnf:/etc/mysql/my.cnf -p 3306:3306 maloute/mariadb
```

## Autostart au boot
- Faire un `cd` vers le répertoire où se trouve le fichier `docker-mariadb.service`
- Activer le service systemd via la commande suivante:
```
# systemctl enable /srv/docker/mariadb/docker-mariadb.service
Created symlink from /etc/systemd/system/multi-user.target.wants/docker-mariadb.service to /srv/docker/mariadb/docker-mariadb.service.
Created symlink from /etc/systemd/system/docker-mariadb.service to /srv/docker/mariadb/docker-mariadb.service.
```
