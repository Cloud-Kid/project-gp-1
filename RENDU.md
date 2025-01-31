# Groupe 1
Membres : 
- ROUBY Nicolas
- OUEDARBI Ilyas
- LUSVARDI Raphael
- BLACHERE Hugo

# Lien du projet GIT
https://github.com/Cloud-Kid/project-gp-1

# Guide utilisateur
Pour déployer la solution, rendez-vous dans le répertoire courant de votre Chart HELM et exécutez la commande suivante :
``` helm install grp1 ```

Si vous vous effectuez des modifications, vous pouvez mettre à jour votre chart en utilisant :
``` helm upgrade grp1 . ```

Pour stopper la chart HELM utilisez :
``` helm uninstall grp1 ```

# Les values
Le fichier values.yaml permet de définir les variables à utiliser.

### Définition de l'image de conteneur à utiliser pour mediawiki
``` 
mediawiki:
  image: harbor.kakor.ovh/public/mediawiki:latest
```

### Définition de l'image de conteneur à utiliser pour mysql
```
mysql:
  image: harbor.kakor.ovh/public/mysql:latest
```

### Définition du mot de passe la base de données
```
  password: "SuperSecurePassword123"
```

### Définition des labels
1. Groupe
2. Environnement (Prod/DEV)

```
label:
  group: "grp1"
```
```
  environment: "DEV"
```

# Définition des varaibles d'environnement
1. Nom de la base de données
2. Nom d el'hôte de la base de données
3. Numéro de port de la base de données

```
env:
  MEDIAWIKI_DB_NAME: mediawiki
  MEDIAWIKI_DB_HOST: mysql
  MEDIAWIKI_DB_PORT: "3306"
```

# Définition des ressources à allouer
```
resources:
  mediawiki:
    limits:
      cpu: "500m"
      memory: "512Mi"
    requests:
      cpu: "250m"
      memory: "256Mi"
  mysql:
    limits:
      cpu: "500m"
      memory: "512Mi"
    requests:
      cpu: "250m"
      memory: "256Mi"
```

# Définition de la valeur storage
storage: true

# Définition du partage NFS
nfs:
  server: 192.168.1.56
  path: /Volume1/public/nfs-share-openshift/groupe-1