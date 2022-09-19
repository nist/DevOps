# Prometheus

## Introduction

Prometheus est un outil de surveillance de système et de collecte de données sérielles temporelles.

Il fut implanté en Go originellement à SoundCloud et est indépendant maintenant.

Il peut être à la fois être utilisé sur des serveurs traditionnels et sur des conteneurs (p/e Kubernetes, Docker Swarm).

Il est utile lors de problèmes (service cessant de fonctionner p/e), mais également à titre préventif (augmentation de la charge, ressources atteignant un seuil critique, lenteur, etc.).

3 composantes du serveur Prometheus :

1. Time series DB => stores metrics data
2. Data Retrieval Worker => pulls metric data from services and store them in DB
3. Web server

targets : cpu, memory, disk, request count, exception count, request duration, etc.

metrics : units of the target

3 types of metrics :

1. Counter
2. Gauge
3. Histogram

Each service needs to expose the needed metric => exporter

Custom : Prometheus library for the progr lang.

Différence avec New Relic : 

Prometheus = Pull, New Relic = Push (need a daemon)

La configuration se trouve dans le fichier `prometheus.yml`.

Le serveur écoute sur le port `9090` par défaut.

PromQL est le langage d'interrogation.

Alertmanager => Envoie les alertes selon la configuration.

Grafana peut être employé pour générer des graphiques à partir des données.

Prometheus est fiable => indépendant.

Compatible avec Docker et Kubernetes.

## Useful commands

[Metrics](http://localhost:9090/metrics)

Requête HTTP ayant un status dans les 400 : `http_requests_total{status!~"4.."}`


## Best practices

* Keep config in git.
* Use Helm chart to deploy operator.
* 


## References

* [Prometheus](https://prometheus.io/)
* [Présentation video](https://www.youtube.com/watch?v=h4Sl21AKiDg&t=0s&ab_channel=TechWorldwithNana)
* [Exporters list](https://prometheus.io/docs/instrumenting/exporters/)
* [Client libraries](https://prometheus.io/docs/instrumenting/clientlibs/)
* [Prometheus Operator](https://prometheus-operator.dev/)