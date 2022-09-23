# DevOps

Base de connaissances pour DevOps

## DevOps 101

Rien de mieux qu'enseigner un sujet si nous voulons savoir si nous le maîtrisons. Voici une brève introduction à DevOps.

Traditionnellement, les développeurs programmaient des applications sur leur ordinateur, puis les rendaient disponibles via un médium quelconque (disquette, cdrom, serveur, etc.). Le processus pouvait être fastidieux et nécessiter du temps.

En ce monde de la quasi instantanité, les applications doivent être rendues disponibles beaucoup plus rapidement et efficacement. Tout un champ d'expertise fut développé en ce sens : DevOps, contraction de Development et Operations. Pour bien comprendre le tout, il faut quelques connaissances techniques.

### Virtualisation

Avec la modernisation des processeurs, il est devenu possible de créer un ordinateur virtuel : simuler un processeur, sa mémoire et son espace disque. Cette technique fut employée pour faciliter le déploiement des applications. Il était alors possible de préparer une machine virtuelle en développement et de la multiplier en production. Mais cette solution avait aussi des inconvénients : elle consomme tout de même beaucoup de ressources (espace disque, CPU, mémoire) et contient trop d'éléments superflus pour l'application.

Une autre solution a alors émergé : un conteneur. Au lieu de contenir tout un ordinateur virtuel avec son système d'exploitation, elle contient que le strict nécessaire pour l'application qu'il contient, reposant sur l'ordinateur hôte pour les ressources. Pour comprendre le tout, cela ressemble à ce que FreeBSD appelle [jail](https://docs.freebsd.org/en/books/handbook/jails/) : pour un système de type unix, tout est un fichier. La racine du système, `/` permet de voir tout le système en autant que nous ayons les droits pour le faire. Il est possible de changer la racine du système dans un sous-répertoire avec `chroot`. Par exemple, si un utilisateur est configuré pour qu'il soit confiné qu'à son répertoire (chroot), `/home/user`, pour lui, la racine du système sera son dossier et il ne verra rien d'autre. Le jail limitera aussi à voir que les commandes auxquelles il a accès, ses processus et le sous-réseau qui lui est attribué. Il est confiné à un carré de sable qui constitue sont univers.

C'est ce concept qu'implante un conteneur : un espace confiné dans lequel une application est déposée. Il devient alors aiser de partager ce conteneur et de le déployer sur différentes infrastructures, tout en limitant les risques de débordement et de sécurité.

[Docker](https://www.docker.com/) est la solution la plus populaire présentement pour effectuer le tout.

## Orchestrer

Les conteneurs ont tendance à se multiplier rapidement. Par exemple, une application web pourrait avoir besoin d'une base de données et d'un serveur web. Trois conteneurs (app, BD, serveur web) à déployer en même temps. Peut-être qu'un seul conteneur ne suffira pas lorsque la charge augmente. Par exemple durant le temps des fêtes. Plusieurs instances du conteneur de l'application seront alors créées pour répondre à la demande.

Pour gérer ces conteneurs, nous aurons recours à un chef d'orchestre. Imaginez un port maritime traitant des conteneurs physiques. Des camions viennent et vont, des grues chargent et déchargent les conteneurs des bâteaux, des trains, des camions. Sans un système de gestion efficace, le tout devient chaotique rapidement. 

C'est le même principe avec les conteneurs informatiques. Un logiciel comme [Kubernetes](https://kubernetes.io/) vient alors à la rescousse. Il est alors possible de le programmer pour gérer les conteneurs d'une certaine façon. Par exemple, de déployer les conteneurs app, BD et serveur web en même temps. Ou de multiplier les conteneurs d'application lorsque la charge atteint un certain seuil. 

## Script

Écrire un paquet de fichiers de configuration pour dire quoi faire au chef d'orchestre devient rapidement difficile et sujet aux erreurs. Des outils ont alors été conçu pour faciliter la vie en ce sens, tel que [Helm](https://helm.sh/). Il est alors possible de gérer des paquets et des modèles de configuration, puis générer le tout dynamiquement.

## Monitor

C'est bien beau avoir tout cela, encore faut-il connaître l'état des conteneurs et de leur contenu. 

* Est-ce que l'application fonctionne ?
* Est-ce que le serveur web est surchargé ?
* Est-ce que la base de données est sur le point de manquer d'espace disque ?

Des logiciels de monitoring viennent alors à la rescousse.

Il existe essentiellement deux types de logiciels de monitoring :

**Push**

C'est la responsabilité de chaque composante d'alimenter le monitor. Par exemple, un serveur va indiquer à interval regulier qu'il est en vie au logiciel de monitor.

Pour ce faire, il faut installer un daemon, un logiciel s'exécutant en arrière-plan, pour envoyer les informations requises au monitor.

**Pull**

Cette fois, c'est la responsabilité du logiciel de monitoring d'aller quérir les données dont il a besoin. Les composantes ne font que les rendre disponibles d'une certaine façon au monitor.

Ces deux approches ont leurs avantages et leurs inconvénients. [Prometheus](https://prometheus.io/) est un logiciel de monitoring de type *pull* populaire pour surveiller ce genre d'infrastructure.

## Et DevOps dans tout cela ?

Le travaille de DevOps consiste donc à trouver des solutions efficaces pour accroître l'automatisation et la vélocité du développement, tout en assurant le maximum de fiabilité au système.

C'est un domaine qui ne cesse d'évoluer, de nouveaux défis et de nouvelles solutions ne cessant d'émerger. Voici maintenant de ces éléments plus en détails.

## concepts
* [CAAS](concepts/caas.md)
<!-- * [Edge](concepts/edge.md) -->
<!-- * [FAAS](concepts/faas.md) -->
* [Infrastructure as Code](concepts/iac.md)
<!-- * [Monorepo vs Multirepo](concepts/mono_multi.md) -->
<!-- * [Serverless](concepts/serveless.md) -->
<!-- * [Site Reliability Engineering](concepts/sre.md) -->

## Container
* [Docker](container/docker.md)
<!-- * [Istio](container/istio.md) -->
* [Kubernetes](container/kubernetes.md)

## Cloud
<!-- * [AWS](cloud/aws.md) -->
* [Microsoft Azure](cloud/azure.md)
<!-- * [Google Cloud](cloud/google.md) -->
<!-- * [Heroku](cloud/heroku.md) -->

<!-- ## Serverless
* [Firebase](serveless/firebase.md)
* [Nbase](serveless/nbase.md)
* [Pocketbase](serveless/pocketbase.md)
* [Supabase](serveless/supabase.md)
 -->
## Config
<!-- * [Ansible](config/ansible.md) -->
* [Helm](config/helm.md)
* [Terraform](config/terraform.md)

<!-- ## CI/CD
* [Argo CI](cicd/argo.md)
* [GitHub Actions](cicd/github_actions.md)
* [GitLab](cicd/gitlab.md)
* [Jenkins](cicd/jenkins.md)
 -->
## Monitoring
<!-- * [Fluent Bit](monitoring/fluent_bit.md)
* [Grafana](monitoring/grafana.md) -->
* [Prometheus](monitoring/prometheus.md)
