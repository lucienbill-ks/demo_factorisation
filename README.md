# Factorisation de code SenseTalk (Eggplant)

Ce dépôt de code propose une façon de factoriser du code de test automatisé.

Les principes : 
- un script de test doit être lisible par une personne non technique (exemple : `demo_factorisation.suite\Scripts\tests\test_edit_in_github.script`)
- les fonctions sont rangées : 
    - par application testée (puis, si besoin, par sous-catégorie métier)
    - dans un fichier "action" s'il s'agit d'une action (exemple : je me connecte à github)
    - dans un fichier "validation" s'il s'agit d'une action (exemple : je vérifie que vs code online s'est bien ouvert)
    - dans "_lib" s'il s'agit d'une fonction interne ou technique, telle que "lire la valeur X dans les variables d'environnement"

C'est un projet en cours, et comme toute solution dans l'informatique : elle fonctionne mieux dans certains contextes que d'autres.
Autrement dit : il ne faut pas hésiter à l'adapter à votre contexte.

## Pour exécuter la démo
Pré-requis:
0. Avoir une license Eggplant Functional
1. Avoir un compte GitHub, avec une authentification à 2 facteurs avec mot de passe à usage unique (OTP)
2. Avoir un coffre Keepass avec ces identifiants dedans (dont l'OTP)
3. Avoir une clé de cryptage en variable d'env système "EPF_SECRET_KEY"
4. Avoir mis à jour la version cryptée du mot de passe de la BDD Keepass