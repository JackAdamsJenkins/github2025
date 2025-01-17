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

## En savoir plus sur le langage markdown
Pour la rédaction de vos fichiers Readme, n'hésitez pas à vous pencher sur la documentation markdown. Voici un lien pour vous aider : [Lien vers documentation](https://www.markdownguide.org/basic-syntax/)

## Éviter d'envoyer des fichiers/dossiers sur Github

Vous avez la possibilité de dire à Github qu'il y a certains fichiers et dossiers que vous ne souhaiteez pas partager sur votre repository.

Pour cela, vous allez devoir :
* Créer un fichier .gitignore à la racine de votre dossier/projet
* Dans le fichier .gitignore, vous devez ajouter ligne par ligne les fichiers/dossiers que vous ne souhaitez pas ajouter à votre repository.

### Exemple de fichier .gitignore
```
# Ceci est un commentaire pour le gitignore
# Vous pouvez mettre des commentaires dans votre fichier
code.js
node_modules
css
img
notadded.js
.env
```

### Exercice
* Dans un de vos repository, ajoutez un nouveau fichier (.js, .html, .autre, on s'en fiche)
* Une fois le fichier ajouté, publier la modification sur github (votre repo doit avoir le fichier)
* Débrouillez-vous ensuite pour supprimer le fichier que vous venez d'ajouter et répercuter la suppression sur votre repo github

### Exercice 2 
* Créez un dossier dans votre repo git
* Ajoutez un fichier dans ce dossier
* Ajoutez un fichier .gitignore dans votre projet
* Publiez la modification sur github
* Vous ne devez PAS avoir le nouveau dossier dans votre repo github

## Récupérer votre travail
Pour récupérer votre travail sur une autre machine, ou simplement récupérer la dernière version en date, vous devez utiliser la commande `git clone URL_DU_REPOSITORY`

par exemple : `git clone https://github.com/JackAdamsJenkins/github2025.git`

Si vous clonez votre repo, vous allez être capable de continuer à travailler sur votre projet.

Si vous clonez le repo d'un autre utilisateur, vous ne pourrez pas l'envoyer sur Github tel quel.
Il faudra vous rendre dans le dossier de votre projet et supprimer le dossier `.git` qui est caché.
Vous pouvez ensuite envoyer le repo sur vote compt Github (git init, git add, git commit, git push...).

## Pull Request
C'est une fonctionnalité clé des système de gesion de version basées sur git comme Github, Gitlab, BitBucket... Elle représente une demande de fusion des modifications (commits) d'une branche vers une autre, généralement de la branche d'une fonctionnalité vers la branche principale d'un projet.

### Concept de la Pull Request (PR)
**Collaboration et revue de code** : La PR n'est pas seulement un mécanisme de fusion de code. C'est aussi un outil de collaboration. Lorsqu'un développeur soummet une PR, d'autres membres de l'équipe peuvent la consulter, laisser des commentaires, suggérer des modfications et même proposer des commits pour améliorer la PR avant qu'elle ne soit fusionnée.

**Point de contrôle** : Avant la fusion, la PR fournit un point de contrôle pour s'assurer que le code respecter les qualités, passe tous les tests et n'introduit pas de régressions.

**Intégration avec CI/CD** : Les PR sont souvent intégrées avec des outils d'Intégration Continue (CI) et de Livraison Continue (CD). Lorsqu'un PR est soumise, des tests automatisés peuvent être déclenchés, et le résultat de ces tests est souvent signalé directement dans l'interface de la PR.

### Faire une Pull Request (PR)
#### Fork du repository
Avant de pouvoir soumettre une PR, vous devez avoir une copie du repository sur votre compte Github. Si ce n'est pas déjà fait :
1. Aller sur la page Github du projet auquel vous souhaitez contribuer.
2. Cliquer sur le bouton "Fork" situé en haut à droite de la page. Cela créera une copie du projet sur votre compte Github personnel.

#### Cloner le fork
Après avoir fait un fork, vous allez pouvoir travailler dessus. Pour cela, vous allez devoir le cloner sur votre propre machine :
```
git clone URL_DU_DEPOT (attention, c'est VOTRE repo que vous devez cloner, pas celui du projet original)
git clone https://github.com/JackAdamsJenkins/hagileolivia.git
```

#### Créer une nouvelle branche
Il est conseillé de créer une nouvelle branche pour chaque nouvelle fonctionnalité ou correction. Cela vous permet de garder le travail organisé et séparé.

Pour créer une nouvelle branche, vous devez utiliser la commande `git checkout -b NomDeLaNouvelleBranche`

##### Exemple
```
git checkout -b nom_de_la_branche
git checkout -b interfaceGUI
git checkout -b correctionBug
git checkout -b search
```
##### Apporter les modifications
Modifier le/les fichiers nécessaires et ajoutez-les à l'index : `git add nomDuFichier`

Ou pour ajouter tous les fichiers modifiés d'un coup : `git add *`

Ensuite, faites un commit de vos modifications : `git commit -m "message de commit"`

##### Pousser la branche vers le fork
```
git push origin nom_de_labranche
git push origin search
```

#### Créer la Pull Request
1. Aller sur la page Github de votre fork
2. Aller sur l'onglet "Pull requests" et cliquer sur le bouton "New pull request"
3. Sélectionner votre nouvelle branche dans le menu déroulant "Compare"
4. Assurez-vous que la branche de base (main) est celle du projet ORIGINAL et non celle de votre fork
5. Vérifier les modifications et cliquer sur "Create Pull Request"
6. Donner un titre à votre PR et décrire les modifications ou les raisons de votre PR
7. Cliquer sur "Create pull request" pour soumettre votre PR

## Exercice PR :
* Rendez-vous sur ce repository https://github.com/JackAdamsJenkins/github2025
* Faites un fork du repo
* Faites un clone
* Ajoutez un fichier VotrePrenom.md à la racine du repo et ajoutez-y votre prénom
* Envoyez le fichier sur votre repo
* Faites une PR

