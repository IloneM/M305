# M305
Notes de cours du module d'Algèbre M305 du [L3-MFA](http://webens-ng.math.u-psud.fr/L3/#Specification MFA) de l'[Université Paris Sud](http://www.u-psud.fr/fr/index.html)
Réalisées d'après l'enseignement de [François Charles] (http://www.math.u-psud.fr/~fcharles/)

## Notes à l'intention des étudiants de L3-MFA
Le cours est actuellement en construction, il est donc possible qu'il ne soit pas tout à fait jour selon nos disponibilités. Merci d'avance de bien vouloir nous en excuser et de faire preuve de patience.
Malgré nos efforts de relecture, il est possible qu'il reste des "coquilles" ça et là. Si vous en repérez une, merci de bien vouloir nous la signaler par email (nos adresses sont disponibles sur les listes de diffusions des emails, envoyés par le secrétariat par exemple).

Liste des auteurs actifs:
+ Jade Salmon
+ Nilo Schwencke
+ Cyril Falcon


## Vous souhaitez contribuer?
Alors soyez le bienvenue! Vous pouvez commencer dès maintenant en suivant les instructions ci-dessous:
N.B.: il est nécessaire de maîtriser au moins les bases de [LaTeX](http://www.latex-project.org/) avant de vous lancer dans l'aventure. Si tel n'est pas le cas, vous pouvez néanmoins vous y initier en suivant [cet excellent tutoriel](http://www.latex-howto.be/book/download_fr)

### Instructions d'initialisation

1 	Installer [git](http://git-scm.com/)

2 	Exécuter sur un terminal:
	```
	git clone -b build https://github.com/IloneM/M305 chemin_vers_repertoire
	```
	Où chemin\_vers\_repertoire désigne un chemin vers un répertoire vide sur l'ordinateur local.
	Vous avez désormais accès à la dernière version du projet et vous pouvez commencer à travailler dessus!
4 	Se créer un compte sur [https://github.com/](https://github.com/)

3 	Demander par email à l'adresse iblobnembabiblb2@gbmabibl.cbobm (enlever les 'b') à devenir contributeur en précisant *votre pseudo github*, qui vous êtes et éventuellement pourquoi et comment voulez vous contribuer.

**Attention: les instructions ci-dessus ne sont à exécuter qu'une fois!**

Pour partager votre contribution et bénéficier de celles des autres auteurs, effectuer les instructions suivantes:

### Cycle courant d'instructions à répéter à chaque mise à jour depuis (pull) ou vers (push) le serveur
1
```
git fetch origin
git pull
```
2
À cette étape, il est possible que git indique qu'il y a des "Conflits de fusions" ("Merge conflict"), c'est à dire des incompatibilités entre les fichiers distants et les fichiers locaux. Si ce n'est pas le cas, passer directement à l'étape suivante. Sinon, git indiquera également quels sont les fichiers posant problème. Ouvrir un de ces fichiers. Chercher alors dans le fichier un block de texte de cette forme:
```
<<<<<<< HEAD
tata
=======
toto
>>>>>>> "une longue chaîne de caractères alphanumérques"
```
Ce qui est entre *<<<<<<< HEAD* et *=======* correspond à la version locale du fichier et ce qui est entre *=======* et *>>>>>>> "une longue chaîne de caractères alphanumérques"* correspond à la version distante du fichier.
Il faut alors "résoudre le conflit", c'est à dire écrire explicitement le texte qui se trouvera à cet endroit (en général un mix des deux versions). Par exemple le conflit ci-dessus pourrait être résolue en remplaçant:
```
<<<<<<< HEAD
tata
=======
toto
>>>>>>> "une longue chaîne de caractères alphanumérques"
```
par:
```
toto et tata
```
Une fois que tous les conflits d'un fichier sont résolus, exécuter la commande:
```
git commit -a
```
L'éditeur de texte de votre ordinateur affichera alors un fichier texte de cette forme:
```
Merge branch 'build' of https://github.com/IloneM/M305 into build

Conflicts:
        M305.tex
#
# It looks like you may be committing a merge.
# If this is not correct, please remove the file
#       .git/MERGE_HEAD
# and try again.


# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch build
# Your branch and 'origin/build' have diverged,
# and have 1 and 1 different commit each, respectively.
#   (use "git pull" to merge the remote branch into yours)
#
# All conflicts fixed but you are still merging.
#
# Changes to be committed:
#       modified:   M305.tex
#
```
Effacer les croisillons (signe '#') devant les lignes commençant par "modified:" et enregistrer. Par exemple le fichier texte ci-dessus deviendra après modifications:
```
Merge branch 'build' of https://github.com/IloneM/M305 into build

Conflicts:
        M305.tex
#
# It looks like you may be committing a merge.
# If this is not correct, please remove the file
#       .git/MERGE_HEAD
# and try again.


# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch build
# Your branch and 'origin/build' have diverged,
# and have 1 and 1 different commit each, respectively.
#   (use "git pull" to merge the remote branch into yours)
#
# All conflicts fixed but you are still merging.
#
# Changes to be committed:
       modified:   M305.tex
#

```

Recommencer ensuite pour tous les fichiers présentant un conflit (heuresement peu nombreux en général); en cas d'oubli des fichiers concérnés, les commandes:
```
# sous linux:
git ls-files -u | cut -f 2 | sort -u
# ou sur tout os (regarder les lignes commençant par 'U')
git pull

```
rappeleront tous les conflits restant à traiter.

3 *Cette étape n'est à suivre que si vous souhaitez modifier des fichiers*
Modifier les fichiers selon votre convenance. Il est conseillé de taper la commande suivante après chaque modification ou séries de modifications importante:
```
git commit -a
```
L'éditeur de texte de votre ordinateur affichera alors un fichier texte de cette forme:
```
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch build
# Your branch is ahead of 'origin/build' by 2 commits.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
#       modified:   M305.tex
#

```
Décommenter les lignes en dessous de *# Changes to be committed:* puis ajouter éventuellement un message (cela est fortement conseillé!) décrivant les modifications apportées en haut du fichier puis enfin enregistrer. Par exemple le fichier texte ci-dessus deviendra après modifications:
```
Un message pour décrire les modifications
avec éventuellement plusieurs lignes

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch build
# Your branch is ahead of 'origin/build' by 2 commits.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
       modified:   M305.tex
#

```
Il est également possible d'utiliser une version légérement modifiée de la commande ci-dessus qui permet de joindre le message directement et de ne pas avoir à éditer le fichier text:
```
git commit -a -m "mon message"
```
S'il est nécessaire d'annuler une modification (un commit), cela peut-être réalisée au moyen de la commande suivante (**à utiliser avec précaution! Les modifications peuvent être perdue définitivement!**):
```
git commit --amend
```
**Une fois les modifications terminées retourner à l'étape 1 avant de procéder à la mise à jour vers le serveur (push) en sautant cette étape, passant ainsi directement à l'étape 4**

4
Arriver à cette étape, il ne reste plus qu'à sauvegarder sur le serveur au moyen de la commande suivante:
```
git push origin build
```
Le terminal devrait alors vous demander votre identifiant github (créer lors des instructions pour débuter):
```
Username for 'https://github.com': 
```
Puis une fois celui entrer, votre mot de passe github:
```
Password for 'https://Ilonem@github.com': 
```
Si tout se passe bien vous devriez voir apparaître quelque chos comme cela:
```
Counting objects: 9, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 946 bytes | 0 bytes/s, done.
Total 9 (delta 6), reused 0 (delta 0)
To https://github.com/IloneM/M305
   b3fc173..150a9ac  build -> build

```
Sinon, ce peut être un problème d'identifiants:
```
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/IloneM/M305/'
```
Ou bien ce peut être un "conflit de fusions":
```
To https://github.com/IloneM/M305
 ! [rejected]        build -> build (fetch first)
error: failed to push some refs to 'https://github.com/IloneM/M305'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
Ceci se produit si, par malheur, quelqu'un vous a devancé et a réalisé un "push" juste avant vous, auquel cas, il faut recommencer tout ce cycle d'instructions (en sautant l'étape 3)... Heuresment ce type d'incident ne devrait se produire que très très rarement!

### Pour aller plus loin
Même si les instructions ci-dessus sont en théorie suffisantes pour que tout fonctionne correctement, pour plus de commodité à l'utilisation et afin d'éviter au maximum les erreurs, il est vivement conseillé de lire les pages suivantes:
+http://git-scm.com/book/fr/v1/Les-branches-avec-Git-Brancher-et-fusionner%C2%A0%3A-les-bases
+http://git-scm.com/book/fr/v1/Les-branches-avec-Git-Gestion-de-branches
+http://git-scm.com/book/fr/v1/Les-branches-avec-Git-Les-branches-distantes
La lecture de tout le [chapitre 3](http://git-scm.com/book/fr/v1/Les-branches-avec-Git) voire de [tout le tutoriel](http://git-scm.com/book/fr/v1) est évidemment souhaitable, mais ne devrait pas être indispensable pour l'utilisation qui est faite de git dans ce projet.

## Licence d'utilisation
Les fichiers téléchargeables peuvent-être utilisés sans aucune contraintes, mais ne peuvent être modifiés sans faire l'object d'une redistribution open-source.
Se référer à la [licence complète](https://github.com/IloneM/M305/raw/master/LICENSE) pour plus d'informations.
