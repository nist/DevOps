# Infrastructure as Code

## Introduction

Traditionnellement, pour développer une application, il fallait préparer un environnement où elle pourrait s'exécuter : système d'exploitation, librairies, services comme une base de données. Cet environnement devait par la suite être reproduit sur un serveur de test, puis un serveur de production. Effectuer le tout manuellement devient rapidement fastidieux et propice aux erreurs, sans compter la maintenance nécessaire pour suivre les mises à jour des différentes composantes.

Une solution fut donc de considérer l'infrastructure comme une application, en utilisant des scripts pour préparer et configurer l'environnement. Des modèles de fichiers de configuration sont alors employés ainsi que des fichiers contenant les valeurs des variables. Des outils comme [Puppet](https://puppet.com/) et [Chef](https://www.chef.io/) ont facilité le travail.

Avec l'adoption d'une infrastructure dans le cloud, d'autres outils ont été développés pour s'accorder aux besoins. Par exemple, [Terraform](https://www.terraform.io/) et [Ansible](https://www.ansible.com/).

C'est cela l'infrastructure en tant que code.  


## Best practices

* Le code est la vérité.
* Le code est conservé dans un gestionnaire de versions (ex. git).
* Le code est testé et surveillé.

## References

* [What Is Infrastructure as Code?](https://stackify.com/what-is-infrastructure-as-code-how-it-works-best-practices-tutorials/)
* [What Is Infrastructure as Code? (video)](https://www.youtube.com/watch?v=zWw2wuiKd5o&ab_channel=IBMTechnology)
* [What is Infrastructure as Code? Difference of Infrastructure as Code Tools](https://www.youtube.com/watch?v=POPP2WTJ8es&ab_channel=TechWorldwithNana)