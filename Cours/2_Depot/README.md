# 2 - Créer et manipuler un dépôt local

Pour créer un dépôt local:
```sh
mkdir mon-dossier
cd mon-dossier
git init # Initialise un nouveau dépôt dans le répertoire courant
code .   # Pour ouvrir notre IDE
```

~~Git créer par défaut une branche _master_~~ <br/>
Le contenu du dépôt est hébergé dans le dossier _.git_ généré<br/>

Nous pouvons visualiser son contenu avec la commande ```ls -la .git```

## Trois zones

Après l'initialisation de notre dépôt, nos fichiers évoluent entre trois zones :
* Le répertoire de travail qui correspond au dossier du projet stocké sur le disque dur,
* L'index où l'on trouve les fichiers en attente de commit,
* Le dépôt qui contient tous les commits (toute l'historique).

```git status``` permet de visualiser l'état des fichiers
<br/>

![Trois_zones.pgn](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/2_Depot/Trois_zones.png)


## Ajouter des fichiers dans l'index

```sh
git add mon_fichier  # Pour ajouter le fichier "mon_fichier"
git add -A           # Pour ajouter tous les fichiers
```

## Retirer des fichiers de l'index

```sh
git restore --staged <file>
```

## Ajouter des fichiers au dépôt

```sh
git commit -m "lorem ipsum"
```

Cette commande est l'élément central de Git. <br/>
Le [commit](https://git-scm.com/docs/git-commit/fr) _doit_ représenter un ensemble de modifications cohérentes entre elles.

## Visualiser les détails des commits

```sh
git log
git log -1 # -1 Pour afficher le commit le plus récent
git reflog # Log les commits et toutes les actions réalisées en local
```

## Identifier l'auteur d'une ligne de code

```sh
git blame mon_fichier
```

## Revenir en arrière

### Git revert

```git revert```permet de revenir à l'état précédent en faisant un nouveau commit.<br/>
Le commit visé par la commande ```git revert```n'est pas supprimé, nous revenons à l'état précédent avec un nouveau commit.<br/>
L'historique est ainsi conservé.<br/>

### Git reset

```git reset```va revenir à l'état précedent sans créer de nouveau commit.

```sh
git reset notreCommitCible --hard # Permet de revenir à n'importe quel commit en supprimant tout ce qui est ultérieur
git reset notreCommitCible --mixed                 # Permet de revenir juste après le commit cible sans supprimer les modifications en cours
git reset notreCommitCible --soft # Permet de se placer sur un commit spécifique afin de voir le code à un instant donné
```

### Modifier le message du précédent commit

```sh
git commit --amend -m "Test" # Modifie le message du précédent commit
```

### Mettre de côté ses modifications avec Git stash

```sh
git stash --include-untracked # Sauvegarde le répertoire de travail et l'index
git stash list                # Liste les stashs d'un dépôt
git stash apply stash@{0}     # Récupère les modifications contenues dans le dernier stash
git stash drop stash@{0}      # Supprime le stash
```

---

⬅️ [1_Configuration](https://github.com/nicolas-sanch/versions-du-code-source/1_Configuration/blob/main/README.md) | [3_Branches](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/3_Branches/README.md)  ➡️
