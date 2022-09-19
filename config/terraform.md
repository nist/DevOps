# Terraform

## Introduction

Outil permettant de créer et mettre à jour l'infrastructure.

Terraform est déclaratif, non procédural.

En clair, nous déclarons le résultat désiré, non la recette pour l'obtenir.

Deux éléments clefs de Terraform :

1. State : état de l'infrastructure
2. statefile (.tfstate) : fichier json contenant la liste des ressources gérées par Terraform.

## Useful commands

Command `cmd`

## Best practices

* Modifier le statefile uniquement avec les commandes de terraform (pas d'édition manuelle avec un éditeur).
* Toujours utiliser un espace de stockage partagé distant afin de partager le statefile (exemple : Terraform Cloud ou Amazon S3 bucket).
* Utiliser un verrou sur l'état pour éviter que 2 personnes le modifient en même temps.
* Faire un backup du state file. Par exemple, avec le versioning.
* Utiliser un statefile par environnement.
* Héberger les scripts dans Git.
* Considérer le code de Terraform comme le code de n'importe quelle application (review, test, PR).
* Appliquer les changements Terraform uniquement par le CD.


## References

* [Terraform](https://www.terraform.io/)
* [Terraform explained in 15 mins](https://www.youtube.com/watch?v=l5k1ai_GBDE&ab_channel=TechWorldwithNana)
* [8 Terraform Best Practices that will improve your TF workflow](https://www.youtube.com/watch?v=gxPykhPxRW0)