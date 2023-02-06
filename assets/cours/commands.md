# Git : Maîtriser git avec la ligne de commandes

Git est un outil de versionning qui s'utilise principalement en ligne de commandes. Tout d'abord assurez vous d'avoir installer [git](https://git-scm.com/downloads)

## Configurer git

Avant de commencer à versionner un projet git, il est obligatoire de configurer notre git. En effet, pour fonctionner, git à besoin de vous connaître (de savoir qui vous êtes).

Pour cela il suffit les commandes suivante pour dire à git qui nous sommes, nous donner une identité :

```bash
$ git config --global user.email mon-email.com
$ git config --global user.name "John john"
```

> Cette étape est obligatoire pour tout le monde, elle ne se fais qu'une seul fois. Votre email et user.name est entièrement libre ! À vous de choisir ce que vous souhaitez

> **Attention** Ce user.name et user.email aura un impact lors de l'utilisation de « remote » (github, bitbucket, gitlab etc ...)

## Démarrer un projet git

Pour démarrer un projet versionné avec git, il faut tout d'abord choisir un dossier contenant le projet sur notre ordinateur.

> Dans ce support, nous allons démarer avec un dossier vide, cependant vous pouvez très bien démarrer un projet git dans un dossier qui n'est pas vide.

Commençons par créer un nouveau dossier et se rendre à l'intérieur :

```bash
$ mkdir MonProjet
$ cd MonProjet
```

Maintenant que nous avons un dossier vide, nous pouvons démarrer le versionning avec git :

```bash
$ git init
```

> Un petit peu de vocabulaire, un projet versionné avec git porte le nom **repository** (dépot).

> Un projet git n'est ni plus ni moins **un dossier sur votre ordinateur**

Lorsque vous lancer la commande `git init`, `git` ne fais vraiment pas grand chose:

- Il créé un dosier `.git` qui contiendra, commit, indexes et branches. Ce dossier est uniquement utilisé en interne par git, nous vous amusez pas à éditer, modifier ou ouvrir des fichiers de ce dossier.

> Entrainez-vous ! Créer votre premier projet nommé `MonPremierProjetGit` à l'emplacement de votre choix sur votre ordinateur. Utilisé la ligne de commande git (git bash).

## L'index et les commits

Premièrement, commençons par créer un premier fichier :

```bash
$ touch monfichier.html
```

Il est possible de consulter l'état de l'index avec la commande git :

```bash
$ git status
```

> Il n'affiche l'état de l'index c'est à dire : en **rouge** les nouveaux fichiers qui ne sont pas dans l'index en **orange** les fichiers modifié qui ne sont pas dans l'index et en **vert** les fichiers qui sont dans l'index

Pour ajouter un fichier dans l'index il faut utiliser :

```bash
$ git add nomDuFichier.extension
```

> Il est possible d'ajouter **tout les fichiers les rouge et orange** avec une seul commande:
>
> ```bash
> $ git add .
> $ git add -A
> ```

Pour enlever un fichier de l'index :

```bash
$ git reset nomDuFichier.extension
```

> Pour enlever tout les fichier **vert** de l'index :
>
> ```bash
> $ git reset --mixted
> ```
>
> Le **head** veut dire « espace de travaille en cours »

Maintenant que nous pouvons manipuler l'index, il est possible de créer notre premier étape. C'est à dire de prendre tout les fichiers **vert** (ceux qui sont dans l'index) et en faire un étape de notre projet (**commit**) :

```bash
$ git commit -m "Premier message"
```

Une fois le commit réaliser, les fichiers indéxé (**vert**) vont disparaitre car ils seront enregistré dans git :).

> **Entrainez-vous** !
> Créer 3 fichier :
>
> - index.html
> - style.css
> - src/index.js
>
> En utilisant les commande `git status`, `git add` et `git commit` réaliser un premier commit avec le message "Premier commit" avec les fichier `index.html` et `style.css`
>
> En utilisnt les mếme commandes, réaliser un second commit avec le message "Second commit" avec le fichier `src/index.js`
