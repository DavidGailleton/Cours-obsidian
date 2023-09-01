### Base git

`init` : Permet d'initialiser un depot git local dans le repertoire courrant. Cela se traduit par la presence d'un dossier cache `.git/` a la racone du depot.
L'édition ou l'ajout de fichier dans ce repo sera detecteé par Git, pour le viualiser dans le terminal on utilise la commande :  
```shell
git init
```

Le depot git ou repository est le dossier qui contient les données que l'on sougaite versionner. On y trouve un dossier cache `.git./`.

Pour vérifier l'état du dépot git, utiliser la commande :
```shell
git status
```

Renommer la branche principale :
```shell
git branch -m "nom_de_la_branch"
```

Avant de sauvegarder les modifications, il faut ajouter les modifications que l'on souhaite sauvegarder avec la commande :
```shell
git add "nom du fichier"
```

`Commit` : Sauvegarde d'un fichier sur git   

La sauvegarde s"effectue ensuite avec la commande :
``` shell
git commit -m "message de commit"
```

### Git Hub sur Windows

En premier temp il faut générer un clé SSH :
```shell
ssh-keygen -t ed25519 -C "mail@domain.com"
```

Puis faire comme suit : 
```
> Enter a file in which to save the key (/c/Users/YOU/.ssh/id_ALGORITHM):[Press enter]
```

```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

Verifier que ssh-agent est en cours d'éxécution est actif :
```shell
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```

Puis ajouter la clé à ssh-agent :
```shell
ssh-add ~/.ssh/id_ed25519
```

La clé se trouve dans C:\Users\USER\.ssh\id_ed25519.pub

Puis ajouter la clé sur git hub dans >personnal settings>ssh and gpg keys>new ssh key :

![](add_ssh_github.png)

Pour pousser le fichier il faut ajouter le lien ssh git@github.com:UserName/RIPOSITORIE_Name.git :

Supprimer les liens existant :
```shell
git remote rm origin
```

Ajouter le lien ssh :
```shell
git remote add origin git@github.com:UserName/RIPOSITORIE_Name.git
```

Une fois fait, il faut pousser le fichier sur Git Hub avec :
```shell
git push -u origin nom_de_la_branch
```