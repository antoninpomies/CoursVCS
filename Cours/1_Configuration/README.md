# 1 - Installation et configuration de GIT

### Sous Debian

```sh
sudo apt-get install git
git --version
```

[Pour les distributions autres que Debian](http://git-scm.com/download/linux)

### Sous MacOS ou Windows
* [git-scm.com](https://git-scm.com)

Le programme d'installation nous demande de choisir notre éditeur texte préféré :
![Git_install_editor.png](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/1_Configuration/Git_install_editor.png)

New ! Nous pouvons choisir "main" comme nom de branch par défaut.
![Git_install_default_branch.png](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/1_Configuration/Git_install_default_branch.png)

A activer pour utiliser Git depuis d'autres logiciels (IDE ...)
![Git_install_3rd-party_software.png](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/1_Configuration/Git_install_3rd-party_software.png)

### Configuration minimale
```sh
git config --global user.name "Prenom nom"
git config --global user.email email@domaine.extension
```

Ici, nous utilison l'argument --global qui correspond au niveau utilisateur.<br/>
Les différents niveaux de configuration de Git, dont les éléments sont stockés dans différents fichiers sont :
|niveau|argument|fichier|
|---|---|---|
|système|--system|/etc/gitconfig|
|utilisateur|--global|~/.gitconfig|
|dépôt|--local|.git/config|

### Aide

```sh
git --help
git config --help # Pour visualiser le manuel de la commande config
```

### Configuration des paramètres

#### L'éditeur de texte par défaut

Exemple où l'on définit _vi_ comme éditeur par défaut
```sh
git config --global core.editor vi
```

#### Template de message de commit

Un modèle de contenu de commit peut-être instauré ajoutant le fichier [~/versions-du-code-source/1_Configuration/template-commit.txt](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/1_Configuration/template-commit.txt) à la configuration

```sh
git config --global commit.template ~/versions-du-code-source/1_Configuration/template-commit.txt
```

#### Ignorer des fichiers
⚠️ Avant même de créer notre premier projet Git, il est important d'avoir à l'esprit que __certains fichiers ne doivent pas être versionnés__<br/>
C'est en particulier le cas des fichiers de configuration, logs, build, etc ... <br/>
Le fichier [.gitignore](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/1_Configuration/.gitignore) est utilisé pour indiquer à Git de ne pas prendre en compte certains fichiers ([Documentation](https://git-scm.com/docs/gitignore))

#### Définitions d'alias

Pour raccourcir l'appel de commandes git, il est possible de définir des alias tel que dans les exemples suivants :
```sh
git config --global alias.co checkout
git config --global alias.last 'log -1 HEAD'
```

---

⬅️ [Introduction](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/README.md) | [2_Dépôt](https://github.com/nicolas-sanch/versions-du-code-source/blob/main/2_Depot/README.md)  ➡️
