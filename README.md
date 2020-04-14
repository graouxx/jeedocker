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
