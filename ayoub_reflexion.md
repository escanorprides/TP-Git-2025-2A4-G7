Réflexion Technique - Groupe 7
Brahim (Élève 1), Ayoub (Élève 2 & 3)

Après l'ensemble des opérations, le projet présente un historique varié qui témoigne des différentes méthodes de collaboration utilisées :

- La branche main contient désormais la version finale fusionnée via un Squash & Merge.
- L'historique montre l'utilisation du rebase par l'élève 3, ce qui a permis de garder une lignée de commits avant la fusion finale.
- Les traces du merge --no-ff (sans fast-forward) de l'élève 1 sont visibles et permettent de voir graphiquement où les branches ont divergé.
- Les opérations de reset et revert illustrent la gestion des erreurs et le retour en arrière dans l'historique.

2. Différence entre git fetch et git pull

- Git Fetch : Cette commande télécharge les nouveaux commits, fichiers et branches depuis le dépôt distant (GitHub) vers la base de données locale, mais sans modifier vos fichiers de travail actuels. C'est une opération de consultation sécurisée.
- Git Pull : C'est un raccourci qui exécute git fetch suivi immédiatement de git merge. Il tente donc de fusionner automatiquement les modifications distantes dans votre branche actuelle.
- Exemple concret : On préfère utiliser git fetch avant de faire un rebase. Cela permet de voir où en est le travail des collègues sur le serveur sans risquer de créer des conflits immédiats dans notre code en cours.

3. Différence entre git reset et git revert

- Git Reset : Cette commande déplace le pointeur de la branche vers un commit antérieur. Dans sa forme --hard, elle efface définitivement les commits suivants de l'historique local. C'est comme un "retour dans le passé".
- Git Revert : Cette commande crée un nouveau commit qui contient l'inverse exact des changements d'un commit passé. On ne supprime rien, on ajoute une correction qui annule une modification précédente.
- Situation risquée : Utiliser git reset --hard sur une branche partagée (comme main ou master) est extrêmement risqué. Cela réécrit l'historique pour tout le monde ; si des collègues ont basé leur travail sur les commits que vous supprimez, cela créera des erreurs majeures et des pertes de données lors de leur prochain push/pull.
