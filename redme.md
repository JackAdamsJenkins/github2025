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

Dans le cas ou il existe pluisuers fichiers qui commencent avec les mêmes lettres, il vous suffit de continuer à appuyer sur la touche `tab`

Si vous avez plusieurs fichiers à ajouter, MAIS que vous ne souhaitez pas ajouter tous les fichiers qui se trouvent dans votre dossier de travail, vous devez faire plusieurs fois `git add nom_du_fichier` pour chacun des fichiers que vous souhaitez ajouter.

### En résumé : 

* `git init` : Pour initialiser le repo local (sur votre machine)
* `git add *` : Pour ajouter tous les fichiers de votre projet
* `git add .` : La même chose qu'avec `git add *`
* `git add nom_du_fichier` : Ajouter un fichier particulier

Si vous faites par mégarde `CTRL + S` dans votre terminal. Il vous suffit de faire `CTRL + C` pour annuler.

La commande `CTRL + C` vous permet d'annuler la commande en cours d'exécution.