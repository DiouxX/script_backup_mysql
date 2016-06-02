# script_backup_mysql

## Description
Ce script permet de sauvegarder une base de donnée MySQL et de spécifier si l'on
désire transférer le DUMP en local ou sur un serveur distant

## Utilisation

Utilisation du script :

	
-u Nom de l'utilisateur de la database

-m Mot de passe de l'utilisateur de la database

-h Hote contenant la database a backuper

-p Port d'ecoute de la database (default: 3306)

-d Nom de la database

-n Nom du Backup (default: Nom de la database)

-f Dossier du backup si l'on ne désire pas un DUMP distant

-t Chemin de sauvegarde de l hote distant

-P Port SSH de l hote distant (default : 22)

-v Mode verbeux

##Example

Si l'on veut un DUMP distant

```sh
script_backup_mysql -u glpi_user -m glpi -h localhost -d glpinew -n glpi-backup -t root@192.168.1.1:/mnt/backup_server/backup_mysql/glpinew/
```

Si l'on veut un DUMP local

```sh
script_backup_mysql -u glpi_user -m glpi -h localhost -d glpinew -n glpi-backup -f /opt/backup/glpi/"
```

*********
IMPORTANT
*********

Pensez à copier la clef public sur le serveur que vous desirer envoyer le backup ( Pour automatiser la tache de backup)

[user@ordi ~]$ ssh-copy-id -i ~/.ssh/id_dsa.pub root@serveur-distant
