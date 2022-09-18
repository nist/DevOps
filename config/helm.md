# Helm

## Introduction

Helm est un gestionnaire de configuration pour Kubernetes.

Pour certaines applications (exemple : Elastic), la configuration peut être fastidieuse. Helm offre un dépôt de configurations pour différentes applications, un peu à la manière du hub de Docker.

Helm peut également être employé comme un générateur de configurations à partir d'un modèle et de variables.

Enfin, Helm sert également de gestionnaire de publication.

Les configurations se nomment *chartname*.

Le format des fichiers est le *YAML*.

La structure d'un chart est :

```
nom/
	chart.yaml **(métadonnées)**
	values.yaml **(variables)** 
	charts/ **(dépendances)**
	templates/ **(modèles)**
```

## Useful commands

- Install : `helm install <chartname>`
- Upgrade : `helm upgrade <chartname>`
- Rollback : `helm rollback <chartname>`

## Best practices

- Utiliser version >= 3 : Tiller a été éliminé, car il représentait un risque de sécurité.

## References

- [Helm](https://helm.sh/)