# II - Revenir à un état antérieur

## 1 - Git revert

* Utiliser la commande checkout pour revenir à l'état du commit avec pour message _Create blue and orange pages_

* Revenir à la version la plus récente et la tager en _v1.0_ avec le message _Stable version of the website_

* Créer un fichier poc.html avec le contenu suivant

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Proof of concept</title>
  <meta charset="utf-8" />
</head>
<body>
  <h1>Proof of concept</h1>
  <p>We're trying out a <span style="color: #F0F">proof of</span>
  <span style="color: #06C">concept</span>!
    
  <p><a href="index.html">Return to home page</a></p>
</body>
</html>
```

* Commiter avec le message _Add a poc_

* 🖊️ Exécuter ```git log --oneline```

* Restaurer la version stable en " supprimant " le commit le plus récent

* 🖊️ Exécuter ```git log --oneline```

## 2 - Git reset

* Créer un fichier vide.html et le laisser vide

* Ajouter un lien dans la section "Navigation" de _index.html_

* 🖊️ Exécuter la commande ```git status```

Nous avons un fichier suivi et un fichier non suivi à modifier.<br/>

* Pour restaurer index.html à l'état du dernier commit, exécuter ```git reset --hard```
* Pour supprimer vide.html, exécuter ```git clean -f```

* 🖊️ Exécuter la commande ```git status```

---

⬅️ [1_Bases](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/TP1/1_Bases.md) | [3_Branches](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/TP1/3_Branches.md)  ➡️