# I - Les bases

## 1 - Code exemple

* Créer un dossier _my-git-repo_
* Ajouter un fichier _index.html_
* Ajouter le contenu suivant:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>A Colorful Website</title>
  <meta charset="utf-8" />
</head>
<body>
  <h1 style="color: #07F">A Colorful Website</h1>
  <p>This is a website about color!</p>    
  
  <h2 style="color: #C00">News</h2>
  <ul>
    <li>Nothing going on (yet)</li>
  </ul>
</body>
</html>
```

## 2 - Premières commandes

* Initialiser le dossier en un dossier Git ([Lien vers le cours 2_Dépôt](https://github.com/nicolas-sanch/versions-du-code-source/tree/main/2_Depot))

* 🖊️ Exécuter la commande ```git status``` avant et après l'ajout du fichier index.html à l'index

* Effectuer votre premier _commit_

* 🖊️ Visualiser le détail du commit

## 3 - Nouveaux fichiers HTML

* Créer les fichier orange.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>The Orange Page</title>
  <meta charset="utf-8" />
</head>
<body>
  <h1 style="color: #F90">The Orange Page</h1>
  <p>Orange is so great it has a
  <span style="color: #F90">fruit</span> named after it.</p>
</body>
</html>
````

et blue.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>The Blue Page</title>
  <meta charset="utf-8" />
</head>
<body>
  <h1 style="color: #00F">The Blue Page</h1>
  <p>Blue is the color of the sky.</p>
</body>
</html>
```

* La création de ces fichiers nécessites un nouveau commit avec pour message _Create blue and orange pages_

## 4 - Modifications des fichiers

* Modifier index.html en ajoutant le contenu suivant avant la balise ```</body>```

```html
<h2>Navigation</h2>
<ul>
  <li style="color: #F90">
    <a href="orange.html">The Orange Page</a>
  </li>
  <li style="color: #00F">
    <a href="blue.html">The Blue Page</a>
  </li>
</ul>
```

* Ajouter le lien suivant à orange.html et blue.html 
```html
<p><a href="index.html">Return to home page</a></p>
```

* Le message corespondant à cette modification sera _Add navigation links_, exécuter les commandes nécessaires

* 🖊️ Exécuter ```git log --oneline```

---

⬅️ [README](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/TP1/README.md) | [2_Retour-arriere](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/TP1/2_Retour-arriere.md)  ➡️