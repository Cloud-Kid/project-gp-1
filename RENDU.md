# Groupe 1
Membres : 
- ROUBY Nicolas
- OUEDARBI Ilyas
- LUSVARDI Raphael
- BLACHERE Hugo

# Guide utilisateur
Pour déployer la solution, rendez-vous dans le répertoire courant de votre Chart HELM et exécutez la commande suivante :
``` helm install grp1 ```

Si vous vous effectuez des modifications, vous pouvez mettre à jour votre chart en utilisant :
``` helm upgrade grp1 . ```

Pour stopper la chart HELM utilisez :
``` helm uninstall grp1 . ```

## Les values
La variable mysql.password permet de donner un mot de passe utilisateur pour la db, pour modifier votre mot de passe de base de données, modifiez la valeur "password" dans le fichier value.yaml