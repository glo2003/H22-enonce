# Mise en place

## Prérequis

- [Git](https://git-scm.com/downloads)
- [Java 11](https://aws.amazon.com/corretto/)
- [IntelliJ](https://www.jetbrains.com/idea/download/)
  - Version Community ou Ultimate disponible gratuitement avec l'université :)
- [Postman](https://www.postman.com/downloads/)
- [Compte Github](https://github.com/login)

## Étapes

### 1. Création de l'organisation

Créez votre organisation d'équipe sur Github.

1. ⚠️ **1 SEULE PAR ÉQUIPE** ⚠️
2. ⚠️ **FORMAT: GLO2003-H22-eq06** ou **GLO2003-H22-eq11** ⚠️
3. En haut à droite, cliquez sur `+` puis `New organization`
4. À gauche, cliquez sur `Create a free organization`
5. Donnez le nom suivant le format ⚠️ **H22-eq06** ou **H22-eq11** ⚠️
6. Donnez le email au responsable des plateformes de votre équipe
7. ⚠️ **INDIQUEZ l'APPARTENANCE À `Business or institution`** ⚠️ et donnez le même nom que précédemment
8. Ajoutez tous les membres de votre équipe
9. ⚠️ **AJOUTEZ LES AUXILIAIRES ET CORRECTEURS** en tant **QU'ADMINISTRATEURS** ⚠️
    1. vigenere23
10. Remplissez (ou non) le sondage

### 2. Copie du projet

Copiez le template du projet vers votre nouvelle organisation.

1. [Copiez le template](https://github.com/glo2003/H22-projet/generate)
2. Choisissez le `Repository name` (votre choix, peut être `floppa`, `glo2003-projet` ou simplement `projet`)
3. ⚠️ **LE `Owner` DOIT ÊTRE VOTRE NOUVELLE ORGANISATION** ⚠️
4. ⚠️ **DOIT ÊTRE PRIVÉ/PRIVATE!!!** ⚠️

### 3. Setup IntelliJ+Java

Exécutez le projet.

1. Clonez le projet vers votre poste local
2. Ouvrez le projet cloné dans IntelliJ
3. Ajustez vos réglages d'IntelliJ
    1. Allez dans `File > Projet Structure`
    2. Dans l'onglet `Project Settings > Project`
        1. Choisissez la version **11 - Amazon Corretto** comme `Project SDK`
        2. Choisissez la version **11** de Java comme `Project langage level`
4. Démarrez le projet
    1. Cliquez sur la flèche verte en haut à droite
    2. Du texte en rouge devrait s'affiche à la console
        1. C'est normal s'il s'agit de `INFO` ou `WARNING`
        2. Ce n'est pas normal s'il s'agit de `ERROR`
5. Confirmez le fonctionnement7
    1. Créez une route de test dans votre application Java et démarrez-la (ex: route `GET /health` qui retourne `200 OK`).
    2. Ouvrez Postman et créez lancez la requête avec
        1. URL : `localhost:8080/api/health`
        2. METHOD : `GET`
    3. Exécuter la requête devrait retourner `200 OK`
    4. Vérifiez qu'aucun message d'erreur n'est apparu dans la console d'intelliJ.
