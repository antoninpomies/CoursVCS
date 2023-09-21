# 3 - Utiliser les branches et tags

## Les tags

Les tags sont utilisés pour marquer les numéros de version sur des commits
<br/>
La numérotation des versions utilise le système [SemVer](https://putaindecode.io/articles/semver-c-est-quoi/) pour _Semantic Versioning_
<br/>
```sh
git tag v1.0.0
git tag -a v1.0.0 -m "msg du tag" # Le -a indique qu'il s'agit d'un tag annoté

git tag --list                    # Permet de lister les noms des tags
git show v1.0.0                   # Affiche les détails d'un tag
```

## Les branches

### Création et fusion

Une branche correspond à une version parallèle de celle en cours de développement.<br/>
Elle peut servir à développer une nouvelle fonctionnalité ou corriger un bug sans intégrer ces modificationsà la version principale du logiciel.<br/>
Leur fonctionnement est expliqué dans l'article suivant : [Les branches avec Git](https://git-scm.com/book/fr/v2/Les-branches-avec-Git-Les-branches-en-bref)

```sh
git branch                 # Lister les branches
git branch ma-branche      # Créer une nouvelle branche
git checkout ma-branche    # Basculer sur ma-branche
git switch -c ma-branche   # Basculer sur ma-branche (Git>=v2.23)
git checkout -b ma-branche # Créer une branche et bascule dessus
```

Les fusions, également appelées _merges_, correspondent à l'opération de récupération des différences d'une branche vers une autre.<br/>
Leur fonctionnement est illustré dans l'article [Branches et fusions](https://git-scm.com/book/fr/v2/Les-branches-avec-Git-Branches-et-fusions%C2%A0%3A-les-bases)

```sh
git checkout master
git merge <ma-branche>                # Fusionne le contenu de ma-branche dans master
git branch -d <ma-branch>             # Supprime la branche ma-branche (généralement réalisé après une fusion)
git push origin --delete <ma-branch>  # Supprime la branch ma-branche sur le répertoire distant 
```

Lorsque l’on cherche à fusionner un commit qui peut être atteint en parcourant l’historique depuis le commit d’origine, Git se contente d’avancer le pointeur car il n’y a pas de travaux divergents à fusionner — ceci s’appelle un _fast-forward_ (avance rapide).<br/>
Cette exécution est indiqué au développement dans l'_output_ de la commande _merge_ et permet à Git d'être plus efficasse.<br/><br/>

Si les deux mêmes parties d'un fichier ont été modifié différemment, Git nous demandera de choisir entre les deux versions.<br/>
Nous utiliserons la commande ```git status```pour visualiser quels fichiers sont _unmerged_.<br/>
Après la résolution du conflit en éditant le fichier, il faudra ajouter cette résolution à l'index avant d'exécuter la commande ```git commit``` pour finaliser le commit de fusion.<br/>
Il est alors nécessaire de documenter le message de commit pour expliquer comment a été conflit a été résolu et pourquoi ce choix.

### Rebase

⚠️ Avant de poursuivre, il est important de noter qu'il ne faut jamais rebaser un commit déjà poussé sur un dépôt distant.<br/><br/>
Nous avons vu qu'un _merge_ a pour but d'intégrer plusieurs commits cohérents entre eux dans un commit unique.<br/>
Un _rebase_ correspond à une réécriture d'historique, par exemple pour intégrer les commits d'une branche dans une autre.<br/>
Cette fonctionnalité est expliqué dans l'article suivant : [Rebaser](https://git-scm.com/book/fr/v2/Les-branches-avec-Git-Rebaser-Rebasing)

---

⬅️ [2_Depot](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/2_Depot/README.md) | [4_Depots_distants](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/4_Depots_distants/README.md)  ➡️
