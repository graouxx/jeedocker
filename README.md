# jeedocker

## Pré-requis

* Installation docker : https://docs.docker.com/install/linux/docker-ce/centos/
* Installation docker-compose : https://docs.docker.com/compose/install/
* Créer un compte duckdns et un domaine : https://www.duckdns.org/

## Utilisation
 
* Copier ".env.local" dans un fichier ".env" et mettre à jour son contenu.
* Lancer le container

```sh
$ docker-compose up  -d 
```

Ouvrir dans un navigateur http://localhost:8080/

Installation jeedom, 
nom de la bdd : jeedom-db
utilisateur et mdp bdd : jeedom

## Redemarrage auto
Si vous souhaitez un redémarrage automatique au démarrage de la machine, il faut créer un fichier docker-compose-app.service

```# /etc/systemd/system/docker-compose-app.service

[Unit]
Description=Docker Compose Application Service
Requires=docker.service
After=docker.service

[Service]
Type=oneshot
RemainAfterExit=yes
WorkingDirectory=/srv/docker
ExecStart=/usr/local/bin/docker-compose up -d
ExecStop=/usr/local/bin/docker-compose down
TimeoutStartSec=0

[Install]
WantedBy=multi-user.target
```

Puis activer le service pour un démarrage auto :
```
systemctl enable docker-compose-app
```
