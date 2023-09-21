# Git distribué

## Prérequis

* Chaque élève doit avoir un compte github.<br/>
* Créer des groupes de 3-4 élèves et désigner un admin-git

## I - Mise en place

* admin-git créé un dépôt local
* il ajoute un fichier README.md avec le contenu suivant et commit
```txt
01 Nom:
01 Prénom:
02 Nom:
02 Prénom:
03 Nom:
03 Prénom:
04 Nom:
04 Prénom:
```
* il créé sur github un dépôt vide
* il pousse son dépôt local sur github

## II - Avec les droits en écriture

* admin-git invite les autres memebres du groupe (ils doivent communiquer leur id github)<br/>
[Permissions sur Github](https://docs.github.com/en/get-started/learning-about-github/access-permissions-on-github)
* il donne les droits en écriture sur le dépôt au membres
* les membres clônent le dépôt en local
* chacun change le nom et prénom au numéro choisi
* les membres effectuent un pull request<br/>
[Pull request en tant que collaborateur](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

## III - Sans les droits en écriture

* admin-git créé un nouveau dépôt github vide
* il pousse son dépôt local sur github
Les membres doivent passer par l'étape _fork_ et _pull request_ pour transmettre leur contribution.<br/>
[Forker un projet](https://docs.github.com/en/get-started/quickstart/fork-a-repo)<br/>
[Effectuer un pull request sans être collaborateur du projet](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork)<br/>
Une des façon de faire est la suivante :
* les membres commencent par cloner le dépôt de admin-git
* ils modifient le fichier local et commit
* ils retournent sur github pour créer un [fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
* ils déclarent un nouveau remote```git remote add mine https://xxxxxxxx```
* les membres peuvent pousser sur leur fork et créer un pull request pour demander à admin-git d'intégrer leur contribution
<br/>
* La suppression d'un dépôt github se fait en allant tout en bas de la page _settings_
