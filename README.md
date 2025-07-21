# Lucien's demo framework for Eggplant (SenseTalk)

## English version

This code repository shows a way to factorize automated test code.

Principles are:

- A test script should be readable by a non-technical person (example: `demo_factorisation.suite\Scripts\tests\test_edit_in_github.script`)
- Functions are organized:
  - by business domain (tested application, and if needed, by business sub-category)
  - in an "action" file if it's an action (example: *I log into GitHub*)
  - in a "validation" file if it's a validation (example: *I check that VS Code Online has opened correctly*)
  - in "_lib" if it's an internal or technical function, such as *read value X from environment variables*

This is a work-in-progress project, and like any solution in IT: it works better in some contexts than others.  
In other words: don't hesitate to adapt it to your context.

It's mainly an attempt to create a codebase that is:

- Business-oriented  
- Easy for new joiner to grasp  
- Simple to maintain

The key is to factorize while having a code structure that reflects the business actions being tested.

### To Run the Demo

Prerequisites:

0. Have an Eggplant Functional license  
1. Have a GitHub account with two-factor authentication using a one-time password (OTP)  
2. Have a Keepass vault containing these credentials (including the OTP)  
3. Have an encryption key set as a system environment variable named `EPF_SECRET_KEY`  
4. Update the encrypted version of the Keepass database password  

### Other notes
When I code things here, I try to balance 2 things: 

- [Parse, don't validate](https://lexi-lambda.github.io/blog/2019/11/05/parse-don-t-validate/) ; I want to use strong types, and I want my functions to fail as early as possible, while giving me enough contextual data to troubleshoot
- Keep It Stupid Simple ; I don't want my function to have super complex parameters. I think that test automation is mostly a task for functional testers, who are not necessarilly experienced coders with a habit of manipulating Enums

## French version
Ce dépôt de code propose une façon de factoriser du code de test automatisé.

Les principes : 

- un script de test doit être lisible par une personne non technique (exemple : `demo_factorisation.suite\Scripts\tests\test_edit_in_github.script`)
- les fonctions sont rangées : 
    - par domaine métier (application testée, puis si besoin par sous-catégorie métier)
    - dans un fichier "action" s'il s'agit d'une action (exemple : _je me connecte à github_)
    - dans un fichier "validation" s'il s'agit d'une action (exemple : _je vérifie que vs code online s'est bien ouvert_)
    - dans "_lib" s'il s'agit d'une fonction interne ou technique, telle que "_lire la valeur X dans les variables d'environnement_"

C'est un projet en cours, et comme toute solution dans l'informatique : elle fonctionne mieux dans certains contextes que d'autres.
Autrement dit : il ne faut pas hésiter à l'adapter à votre contexte.

C'est surtout une tentative pour faire une base de code :

- Orientée métier
- Qui facilite l'arrivée de nouvelles personnes sur le projet
- Dont la maintenance est simple

La clé, c'est de factoriser en ayant un structure de code qui reflète les actes métiers testés.

### Pour exécuter la démo
Pré-requis:

0. Avoir une license Eggplant Functional
1. Avoir un compte GitHub, avec une authentification à 2 facteurs avec mot de passe à usage unique (OTP)
2. Avoir un coffre Keepass avec ces identifiants dedans (dont l'OTP)
3. Avoir une clé de cryptage en variable d'env système "EPF_SECRET_KEY"
4. Avoir mis à jour la version cryptée du mot de passe de la BDD Keepass


### Autres remarques

Quand je code ici, j'essaie de trouver un équilibre entre deux choses :

- [Parse, don't validate](https://lexi-lambda.github.io/blog/2019/11/05/parse-don-t-validate/)  : je veux utiliser des types forts, et je veux que mes fonctions échouent le plus tôt possible, tout en me fournissant suffisamment de contexte pour diagnostiquer les problèmes  
- Keep It Stupid Simple : je ne veux pas que mes fonctions aient des paramètres trop complexes. Je pense que l'automatisation des tests est principalement une tâche pour des testeur·euses fonctionnelles, qui ne sont pas nécessairement des développeur·euses expérimentées habituées à manipuler des Enums