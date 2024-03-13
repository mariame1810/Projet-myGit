# Projet-myGit 
#Simulation de dépot d'un projet sur git avec gestion des #Branches et des Commis
#By @mariame1810

Procedure de test:
- initaliser le projet: ./myGit init
- creer le dossier tmp: mkdir tmp
- creer 5 files: file1.test, file2.test, etc.
- creer une branche test: ./myGit checkout-branch testBranch
- imprimer la liste: ./myGit refs-list
- on est actuellement sur master, ajouter file1.test a la zone de preparation: ./myGit add file1.test
- afficher la zone de preparation: ./myGit add-list
- vider la zone de preparation: ./myGit clear-add
- verifier qu'elle est bien vide: ./myGit add-list
- ajouter 4 fichiers a la zone de preparation: ./myGit add file1.test ... file4.test
- on commit sur master: ./myGit commit master -m firstCommit
- afficher le contenu de la branche: ./myGit branch-print master
- changer de branch: ./myGit checkout-branch testBranch
- verifier que la branche est bien vide: ./myGit branch-print testBranch
- verifier que la branche courante est bien celle attendue: ./myGit get-current-branch
- on commit 4 autres fichiers, dont 3 en commun avec le commit vers lequel pointe master pour creer un conflit: ./myGit add file2.test ... file4.test file5.test && ./myGit commit testBranch -m mergeConflict
- se repositionner sur master: ./myGit checkout-branch master
- fusionner les branches: ./myGit merge testBranch
- si tout s'est bien passe, file2.test, file3.test, et file4.test sont en conflit sur les deux branches. Choisir "remote" pour mettre le commit de deletion sur testBranch
- verifier que testBranch a bien ete effacee: ./myGit refs-list
- verifier que master pointe bien vers un commit contenant file1.test et file5.test: ./myGit print-branch
