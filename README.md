# Factorisation de code SenseTalk (Eggplant)

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

## Pour exécuter la démo
Pré-requis:

0. Avoir une license Eggplant Functional
1. Avoir un compte GitHub, avec une authentification à 2 facteurs avec mot de passe à usage unique (OTP)
2. Avoir un coffre Keepass avec ces identifiants dedans (dont l'OTP)
3. Avoir une clé de cryptage en variable d'env système "EPF_SECRET_KEY"
4. Avoir mis à jour la version cryptée du mot de passe de la BDD Keepass


## Other notes
When I code things here, I try to balance 2 things: 
- [Parse, don't validate](https://lexi-lambda.github.io/blog/2019/11/05/parse-don-t-validate/) ; I want to use strong types, and I want my functions to fail as early as possible, while giving me enough contextual data to troubleshoot
- Keep It Stupid Simple ; I don't want my function to have super complex parameters. I think that test automation is mostly a task for functional testers, who are not necessarilly experienced coders with a habit of manipulating Enums

