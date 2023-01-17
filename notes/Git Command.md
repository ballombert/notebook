[Et merde, Git!?! (ohshitgit.com)](https://ohshitgit.com/fr)

Corriger le message message
```bash
git commit -amend
```

revenir sur la version du serveur 

```bash
# obtenir la dernière version du serveur
git fetch origin
git checkout master
git reset --hard origin/master
# supprimer les fichiers et répertoires non archivés
git clean -d --force
# répéter checkout/reset/clean pour chaque branche problématique
```

