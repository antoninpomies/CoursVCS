# III - Manipuler les branches

## 1 - La branche POC

* 🖊️ Lister les branches du projet

* 🖊️ Exécuter ```git log --oneline```

* Utiliser ```git checkout``` pour se placer sur le commit _Add a poc_

* Créer une nouvelle branche _poc_ et se placer dessus

* Modifier le fichier poc.html avec le contenu suivant :
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Proof of concept</title>
  <meta charset="utf-8" />
</head>
<body>
  <h1>Proof of concept</h1>
  <p>Look! A Rainbow!</p>

  <ul>
    <li style="color: red">Red</li>
    <li style="color: orange">Orange</li>
    <li style="color: yellow">Yellow</li>
    <li style="color: green">Green</li>
    <li style="color: blue">Blue</li>
    <li style="color: indigo">Indigo</li>
    <li style="color: violet">Violet</li>
  </ul>
    
  <p><a href="index.html">Return to home page</a></p>
</body>
</html>
```

* Commiter avec le message _Add a rainbow to poc.html_

* Renommer poc.html en rainbow.html

* 🖊️ Exécuter la commande ```git status```

* Exécuter la commande permettant d'arrêter de suivre poc.html

* 🖊️ Exécuter la commande ```git status```

* Commiter avec le message _Rename poc.html to rainbow.html_

* 🖊️ Exécuter ```git log --oneline```

* Revenir sur la branche master

## 2 - La branche CSS

* Créer une branche _css_ et se positionner dessus

* Créer le fichier style.css avec le contenu suivant : 
```css
body {
  padding: 20px;
  font-family: Verdana, Arial, Helvetica, sans-serif;
  font-size: 14px;
  color: #111;
}

p, ul {
  margin-bottom: 10px;
}

ul {
  margin-left: 20px;
}
```

* Commiter avec le message _Add CSS stylesheet_

* Ajouter la ligne suivante après la balise <title> dans les fichiers, index.html, blue.html et orange.html
```html
<link rel="stylesheet" href="style.css" />
```

* Commiter avec le message _Link HTML pages to stylesheet_

* 🖊️ Revenir sur la branch master et fusionner la branche _css_ avec celle-ci

* 🖊️ Exécuter ```git log --oneline```

* Supprimer la branche _css_

## 3 - Poursuite du POC

* Se placer sur la branche _poc_ et fusionner avec _master_

* Résoudre le conflit en conservant ```<title>Proof of concept</title>```

* Ajouter une balise ```<link rel="stylesheet" href="style.css" />``` dans le fichier rainbow.html

* Commiter avec le message _Add CSS stylesheet to rainbow.html_

* Ajouter un lien vers rainbow.html dans le fichier index.html

* Commiter avec le message _Link index.html to rainbow.html_

* 🖊️ Exécuter ```git log --oneline```

## 4 - Un arc-en-ciel alternatif

* Créer une branche _poc-alt_ et se placer dessus

* Modifier rainbow.html avec le contenu suivant :
```html
<div style="background-color: red"></div>
<div style="background-color: orange"></div>
<div style="background-color: yellow"></div>
<div style="background-color: green"></div>
<div style="background-color: blue"></div>
<div style="background-color: indigo"></div>
<div style="background-color: violet"></div>
```
* Ajouter le contenu suivant avant ```</head>```
```html
<style>
  div {
    width: 300px;
    height: 50px;
  }
</style>
```

* Commiter avec le message _Make a real rainbow_

## 5 - Le hotfix

* Se placer sur la branche master

* Créer et se placer sur une branche _news-hotfix_

* Modifier les "News" de index.html avec le contenu suivant :
```html
<h2 style="color: #C00">News</h2>
<ul>
  <li><a href="news-1.html">Blue Is The New Hue</a></li>
</ul>
```

* Créer le fichier news-1.html avec le contenu suivant :
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Blue Is The New Hue</title>
  <link rel="stylesheet" href="style.css" />
  <meta charset="utf-8" />
</head>
<body>
  <h1 style="color: #079">Blue Is The New Hue</h1>
  <p>European designers have just announced that
  <span style="color: #079">Blue</span> will be this year's
  hot color.</p>
    
  <p><a href="index.html">Return to home page</a></p>
</body>
</html>
```

* Commiter avec le message _Add 1st news item_

* 🖊️  Fusionner le contenu de _news-hotfix_ dans _master_

* Supprimer la branche _news-hotfix_

## 5 - Fin du poc

* Se placer sur la branche _poc_

* Modifier index.html avec le contenu suivant :
```html
<h2 style="color: #C00">News</h2>
<ul>
  <li><a href="rainbow.html">Our New Rainbow</a></li>
</ul>
```

* Commiter avec le message "Add news item for rainbow"

* 🖊️ Exécuter ```git log --oneline```

* Fusionner le contenu de _poc_ dans _master_

* Pour résoudre le conflit, éditer index.html avec le contenu suivant :
```html
<h2 style="color: #C00">News</h2>
<ul>
  <li><a href="news-1.html">Blue Is The New Hue</a></li>
  <li><a href="rainbow.html">Our New Rainbow</a></li>
</ul>
```

* Effectuer le commit

* Supprimer les branches _poc_ et _poc-alt_ (```git branch -D poc-alt``` permet de supprimer malgré les modifications non fusionnées)

---

⬅️ [2_Retour-arriere](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/TP1/2_Retour-arriere.md) | [4_Rebase](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/TP1/4_Rebase.md)  ➡️