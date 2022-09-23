# Docker

## Introduction

Docker permet de créer et gérer une boîte dans laquelle mettre une application et ses dépendances.

## Sous la couverte

Docker exploite une caractéristique du noyau Linux permettant de créer un environnement cloisonné ayant ses propres identifiants et ses droits (voir [namespace](https://man7.org/linux/man-pages/man7/namespaces.7.html) et [cgroup](https://man7.org/linux/man-pages/man7/cgroups.7.html)).

À la différence d'une machine virtuelle, cette boîte partage les ressources du système hôte : le noyau de l'hôte, sa mémoire, son espace disque.

Bien qu'à l'intérieur du conteneur nous ne voyons pas les ressources de l'hôte, de l'hôte, nous avons accès au conteneur, bien que ses ressources aient des identifiants différents.

## Image

Une image est la recette pour créer un conteneur. Une image peut partir d'une autre image. Pensez à un gâteau à étages avec du glaçage et des garnitures.

Les images sont définies grâce à un fichier de configuration en [**YAML**](https://yaml.org/) nommé [*Dockerfile*](https://docs.docker.com/engine/reference/builder/).

## Hub

[Docker Hub](https://hub.docker.com/) est un dépôt d'images prêtes à l'emploi. Par exemple, des images d'[Ubuntu](https://hub.docker.com/_/ubuntu), de [MySQL](https://hub.docker.com/_/mysql), de [Node.js](https://hub.docker.com/_/node), etc. Celles-ci peuvent servir de point de départ pour créer nos propres images et même être utilisées pour tester un logiciel ou développer.


## Conteneur

Le conteneur est une instance d'une image en cours d'exécution. Pour prendre le vocabulaire de la programmation orientée objet, l'image est un peu comme la classe alors que le conteneur serait l'objet. Ou pour reprendre l'analogie culinaire, l'image est la recette de gâteau et le conteneur est les différents gâteau qui furent fabriqués à l'aide de cette recette.

## Compose

Une application fonctionne rarement en vase clos. Par exemple, une application web dépendra d'un serveur web et d'une base de données. Ce qui ferait possiblement trois images et trois conteneurs interagissant entre eux.

Pour faciliter la gestion d'éléments multiples, [**Docker Compose**](https://docs.docker.com/compose/) permet de les gérer ensemble grâce à un fichier de configuration.

## Swarm

[Docker Swarm](https://docs.docker.com/engine/swarm/) est un mode de gestion des hôtes exécutant des conteneurs. Il permet par exemple la gestion de la montée en charge et des pannes. 

## Scratch

La plupart des images disponibles sur Hub sont assez volumineuses. Elles contiennent un système d'exploitation complet et toutes les dépendances pour le logiciel désiré.

Par exemple, l'image de Go fait près de 1 Go, celle de Python, 900 Mo. Sans compter les problèmes de bugs et de sécurité que représentent d'avoir tous ces éléments dans une image.

Une autre approche serait de créer des images [à partir de rien](https://hub.docker.com/_/scratch), une image vide dans laquelle nous déposons un exécutable Linux autonome. Bien sûr, cela n'est pas envisageable dans tous les cas, mais des langages récents permettent de créer une application statique et autonome.

Quelques exemples :

* [Go](https://www.oreilly.com/content/should-you-containerize-your-go-code/)
* [Rust](https://bxbrenden.github.io/)
* [WebAssembly](https://www.docker.com/blog/why-containers-and-webassembly-work-well-together/)
* [Nim](https://scripter.co/nim-deploying-static-binaries/)

Avec la tendance forte de découper les applications en microservices et un besoin accru de fluidité et de vélocité, je crois que cette approche sera de plus en plus populaire. 

## Commandes

Command `cmd`

## Best practices

- Best pratice 1

## References

- []()