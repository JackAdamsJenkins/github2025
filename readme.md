# Cours Github 2025
## Première étape : initialiser un repo sur Github

* Créer dans le Github, un nouveau repository
* Nommer le repo comme vous le souhaitez
* Vous pouvez choisir sa visibilité :
  * Public : le repo est visible par tous les utilisateurs
  * Private : le repo est visible uniquement par les membres du projet
* La description du repo est facultative
* Aller en bas de la page, et cliquer sur le bouton "Create repository"

Votre repository est maintenant créé, vous allez pouvoir faire votre premier commit.

## Faire son premier commit
Vous allez vous rendre compte qu'il y a un petit encadré nommé "Quick setup" qui propose deux possibilités : SSH et HTTPS.

Si ce n'est pas fait par défaut, choisissez HTTPS.

## Initialisation du Github sur votre machine
Sur Visual Studio Code : 

* Ouvrir un terminal (4 possibilités différentes, vous choisissez) :
   * Menu terminal > Nouveau terminal
   * Menu affichage > Terminal
   * CTRL + ù
   * En bas à gauche, vous avez une icône triangle et rond, cliquez dessus

Vous pouvez maintenant initialiser git sur votre machaine sur le terminal qui est ouvert avec la commande `git init`.

Une fois initialisé, vous allez devoir indiquer quel(s) fichier(s) vous souahitez envoyer sur Github. Pour cela :
* `git add *` : Ajouter tous les fichiers de votre projet
* `git add .` : La même chose qu'avec `git add *`
* `git add nom_du_fichier` : Ajouter un fichier particulier

Pour info, vous ne devez PAS entrer le nom complet du dossier ou du fichier à ajouter. Ca augmente le risque d'erreur. Au lieu d'écrire le nom complet vous-même, vous devez écrire seulement  la ou les premières lettres et appuyer sur la touche `tab`

Dans le cas ou il existe plusieurs fichiers qui commencent avec les mêmes lettres, il vous suffit de continuer à appuyer sur la touche `tab`

Si vous avez plusieurs fichiers à ajouter, MAIS que vous ne souhaitez pas ajouter tous les fichiers qui se trouvent dans votre dossier de travail, vous devez faire plusieurs fois `git add nom_du_fichier` pour chacun des fichiers que vous souhaitez ajouter.

### En résumé : 

* `git init` : Pour initialiser le repo local (sur votre machine)
* `git add *` : Pour ajouter tous les fichiers de votre projet
* `git add .` : La même chose qu'avec `git add *`
* `git add nom_du_fichier` : Ajouter un fichier particulier

Si vous faites par mégarde `CTRL + S` dans votre terminal. Il vous suffit de faire `CTRL + C` pour annuler.

La commande `CTRL + C` vous permet d'annuler la commande en cours d'exécution.

## Faire la liaison avec le repo distant

Vous venez d'initaliser git sur votre machine, mais il ne sait pas encore qu'il doit être lié à votre repo distant (Github). Pour cela, vous allez devoir connecter l'origine à votre repo distant.

Commençons d'abord par ajouter un petit message qui précise ce qu'on a fait comme modification/ajout/suppression.
* `git commit -m "Explication du commit"`
* `git commit -m "Ajout du fichier readme`

Une fois que le message de commit est défini, on va choisir la branche sur laquelle on va travailler.

Lorsque vous souhaitez stocker vos fichiers sur github, si vous le souhaitez, vous pouvez stocker différentes versions de vos fichiers. Cela s'appelle des branches.

La branche principale sur laquelle vos fichiers sont enregistrés doit s's'appeler `main`, par convention.

* `git branch -m main`
* `git branch -m mysql`
* `git branch -m sqlite`
* `git branch -m ceQueVousVoulez`

Cette commande indique qu'on sélectionne la branche `main`

* `git branch -m main`

Il est maintenant temps de connecter votre repo local (votre machine) à votre repo distant (Github). Pour cela, utilisez la commande :

* `git remote add origin LIEN_HTTPS_DE_VOTRE_REPO` Exemple :
* `git remote add origin https://github.com/JackAdamsJenkins/github2025.git`

Maintenant que le repo local et distant sont connectés, il vous rester à envoyer vos fichiers sur Github. Cela se fait avec la commande `git push -u origin main`

### En résumé : 
Voici les commandes à lancer :
* `git init` : Pour initialiser le repo local (sur votre machine)
* `git add *` : Pour ajouter tous les fichiers de votre projet
* `git add .` : La même chose qu'avec `git add *`
* `git add nom_du_fichier` : Ajouter un fichier particulier
* `git commit -m "Explication du commit"`: Pour indiquer le message de commit
* `git branch -m main`: Pour sélectionner la branche principale
* `git remote add origin LIEN_HTTPS_DE_VOTRE_REPO` : Pour connecter votre repo local à votre repo distant
* `git push -u origin main` : Pour envoyer vos fichiers sur Github

### Informations

Pour pouvoir envoyer les fichiers sur Github, la première fois que vous réalisez les commandes, le système va vous demander de vous authentifier. Il faudra renseigner le mail que vous avez utilisé pour créer votre compte Github.

Pour pouvoir configurer le compte Github, il faut entrer la commande :
* `git config --global user.email "votreAdreese@mail.com`


Les commandes `git init`, `git branch` et `git remote add origin` sont à àlancer UNE SEULE FOIS au moment de l'initialisation du repo. Dit autrrment, une seul fois par PROJET.

Une fois que ces commandes ont été faites, pendant le reste du développement de votre projet, vous pouvez utiliser les commandes suivantes : `git add * ou nomDuFichier`, `git commit -m "message de commmit"` et `git push`

/!\ Si vous avez déjà entré des commandes que vous devez relancer (typiquement git add et git push), vous pouvez reprendre les anciennes commandes executés dans le terminal en appuyant sur la flèche "haut" du clavier (ou "bas" pour se déplacer vers le bas).

## Écrire un bon message de commit

Écrire un bon message de commit est essentiel pour la maintenance et la compréhension d'un projet. Cela aide à suivre l'évolution du projet et à comprendre les raisons derrière chaque modification.

Voici une norme généralement acceptée pour rédiger des messages de commit.

### Structure d'un message de commit
Un message de commit se compose généralement de deux parties :
* Un titre (ou en-tête) : C'est une brève description des modifications. Il doit être concis et ne pas dépasser les 50 caractères. il doit commence par une majuscule.
* Un corps : Il donne des détails supplémentaires sur les modifications. Il est séparé du titre par une ligne blanche (ligne vide).

```
Titre court et description

Corps du message : ici, on explique en détail le pourquoi et le comment
des changements si nécessaire. Essayez de garder chaque ligne à moins
de 72 caractères pour la lisibilité.
```

### Conseils pour un bon message de commit
* Utiliser l'impératif : Le titre doit idéalement ^étre écrit à la voix impérative (ex. Ajoute, Corrige, Refactorise  au lieu de Ajouté, Corigé, Refactorisé).
* Titre clair et concis : Doit être court et descriptif
* Séparer les sujets : Si vous avez plusieurs modifications qui n'ont pas de rapport entre elles, envisagez de les séparer en plusieurs commits.
Expliquer le pourquoi, pas le comment : Le code lui-même montre comment une certaine chose à été faite. Ce qui n'est pas toujours clair, c'est pourquoi cette modification à été apportée. Assurez-vous d'expliquer les raisons dans le corps du message.
* Évitez les messages vagues : "Diverses corrections", ou "Mise à jour" ne sont PAS des bons messages de commit.
* Utilisez des références aux issues/tracker : Si votre commit fait référence à une issue ou à un ticket, ajoutez cette référence dans le corps du message.

**Toujours préférer l'utilisation de l'anglais pour vos messages de commit.**

### Exemple d'un bon message de commit

```
Ajoute une fonctionnalité de recherche

La page d'accueil avait besoin d'une fonctionnnalité de recherche
pour aider les utilisateurs à trouver des contenus spécifiques.

Cette modification ajoute un moteur de recherche et utilise l'API
de recherche pour récupérer les résultats.

Relatif à l'issue #123
```

Version anglaise du message de commit (a préferer)
```
Add search functionality

Homepage needed a search feature to help users find specific content.

This change adds a search engine and uses the search API to retrieve
results.

Related to issue #123
```