# IV - Rebasing

## 1 - Section à propos

* Créer et se positionner sur une branche _about_

* Créer un dossier _about_ contenant un fichier index.html vide

* Commiter avec le message _Add empty page in about section_

* Ajouter le contenu suivant dans _about/index.html_
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>About Us</title>
  <link rel="stylesheet" href="../style.css" />
  <meta charset="utf-8" />
</head>
<body>
  <h1>About Us</h1>
  <p>We're a small, colorful website with just two employees:</p>

  <ul>
    <li><a href="me.html">Me: The Developer</a></li>
    <li><a href="mary.html">Mary: The Graphic Designer</a></li>
  </ul>
    
  <p><a href="../index.html">Return to home page</a></p>
</body>
</html>
```

* Commiter avec le message _Add contents to about page_

## 2 - Hotfix

Nous allons à nouveau travailler sur un _hotfix_ nous obligeant à mettre notre développement de côté.

* Basculer sur la branche _master_

* Créer une branche _news-hotfix_ et se positionner dessus (⚠️ Si vous êtes encore dans le dossier _about_, celui-ci n'existe pas dans la branche _master_)

* 🖊️ Lister les branches

* Modifier la section _News_ de index.html avec le contenu suivant
```html
<h2 style="color: #C00">News</h2>
<ul>
  <li><a href="news-1.html">Blue Is The New Hue</a></li>
  <li><a href="rainbow.html">Our New Rainbow</a></li>
  <li><a href="news-2.html">A Red Rebellion</a></li>
</ul>
```

* Commiter avec le message _Add 2nd news item to index page_

* Créer le fichier news-2.html avec le contenu suivant
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>A Red Rebellion</title>
  <link rel="stylesheet" href="style.css" />
  <meta charset="utf-8" />
</head>
<body>
  <h1 style="color: #C03">A Red Rebellion</h1>
    
  <p>Earlier today, several American design firms
  announced that they have completely rejected the use
  of blue in any commercial ventures. They have
  opted instead for <span style="color: #C03">Red</span>.</p>
    
  <p><a href="index.html">Return to home page</a></p>
</body>
</html>
```

* Commiter avec le message _Add article for 2nd news item_

Nous avons terminé notre hotfix, nous allons maintenant intégrer notre correctif à la branche principale.

* 🖊️ Basculer sur la branche _master_ et fusionner _news-hotfix_

* Supprimer la branche _news-hotfix_

Nous voulons récupérer les modifications de la branche _master_ dans notre branche de développement.<br/>
Cette fois-ci, nous utilisons _rebase_ à la place de _merge_

* Basculer sur la branche _about_

* 🖊️ Exécuter ```git rebase master``` puis  ```git log --oneline```

## 3 - Page nous

* Créer un fichier about/me.html avec le contenu suivant 
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>About Me</title>
  <link rel="stylesheet" href="../style.css" />
  <meta charset="utf-8" />
</head>
<body>
  <h1>About Me</h1>
  <p>I'm a big nerd.</p>

  <h2>Interests</h2>
  <ul>
    <li>Computers</li>
    <li>Mathematics</li>
    <li>Typography</li>
  </ul>

  <p><a href="index.html">Return to about page</a></p>
</body>
</html>
```

* Commiter avec le message _Add HTML page for personal bio_

* 🖊️ Exécuter ```git log --oneline```

* Créer un fichier vide about/mary.html et commiter avec le message _Add empty HTML page for Mary's bio_

* Ajouter une section _Navigation_ à my-git-repo/index.html avec le contenu suivant :
```html
<h2>Navigation</h2>
<ul>
  <li>
    <a href="about/index.html">About Us</a>
  </li>
  <li style="color: #F90">
    <a href="orange.html">The Orange Page</a>
  </li>
  <li style="color: #00F">
    <a href="blue.html">The Blue Page</a>
  </li>
  <li>
    <a href="rainbow.html">The Rainbow Page</a>
  </li>
</ul>
```

* Commiter avec le message _Add link to about section in home page_

Nous allons maintenant nettoyer l'historique des commits avant de _merger_ notre feature dans notre branche principale.<br/>
Pour cela, nous allons utiliser un _interactive rebase_.

* Exécuter ```git rebase -i master``` et modifier la liste tel que dans l'exemple suivant
```txt
pick xxxxxxx Add empty page in about section
squash xxxxxxx Add contents to about page
pick xxxxxxx Add HTML page for personal bio
squash xxxxxxx Add empty HTML page for Mary's bio
pick xxxxxxx Add link to about section in home page
```

Ici, nous utilisons la commande _squash_ pour condenser les petits commits, cohérents entre eux, un un seul.

* 🖊️ Exécuter ```git log --oneline```

Nous pouvons observer que les 5 commits présents à l'origine dans _about_ ont été condensé en 3, et 2 d'entre eux ont un nouveau message.<br/>
Aussi, les commit ID sont différents.<br/><br/>

L'_interactive rebasing_ nous permet d'aller encore plus loin.<br/> 
Lorsque Git déplace un commit vers une nouvelle base, nous pouvons modifier l'index avant de le _commiter_.

* Exécuter à nouveau ```git rebase -i master``` et indiquer que nous souhaitons editer avant le second commit.
```txt
pick 58dec2a Create the about page
edit 6ac8a9f Begin creating bio pages
pick 51c958c Add link to about section in home page
```

* Editer about/mary.html en intégrant le contenu ```[Mary, please update your bio!]```

Nous sommes actuellement entre deux commits dans un rebase.<br/>

* 🖊️  Exécuter les commandes suivantes
```sh
git add about/mary.html
git status
git commit --amend  # --amend indique à git d'utiliser le commit existant au lieu d'en créer un nouveau
```

* 🖊️ Pour indiquer à Git que nous avons terminé nos modifications et qu'il peut terminer le rebase, nous utilison la commande suivante : 
```sh
git rebase --continue  # --abort permet d'annuler
```

* 🖊️ Exécuter ```git log --oneline```

Nous allons maintenant conclure le développement de notre feature :

* Basculer sur la branche _master_

* 🖊️ Exécuter ```git log --oneline```

* Fusionner la branche _about_

* 🖊️ Exécuter ```git log --oneline```

* Supprimer la branche _about_

---

⬅️  3_Branches](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/TP1/3_Branches.md)