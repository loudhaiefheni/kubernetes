# Déploiement Nginx sur Kubernetes

Ce guide explique comment déployer un cluster Nginx sur Kubernetes. Kuberne>

## Prérequis

Avant de commencer, assurez-vous que les outils suivants sont installés et >

- Docker: Un outil de création et de gestion de conteneurs.
- Kubernetes: L'orchestrateur de conteneurs pour gérer le cluster.
- Minikube: Un outil qui permet de lancer un cluster Kubernetes localement.


##Configuration

### Démarrage de Minikube
- Lancez Minikube pour créer un cluster local

```bash
minikube start
```
### Vérification du Cluster Kubernetes
- Une fois Minikube démarré, vérifiez que le cluster Kubernetes est correctement configuré et en cours d'exécution avec la commande suivante :

```bash
kubectl cluster-info
```
### Déploiement de Nginx

Le déploiement de Nginx sur votre cluster s'effectue en deux étapes principales : 
- la création du déploiement 

```bash
kubectl apply -f nginx-deployment.yaml
```
- l'exposition du service Nginx.

```bash
kubectl expose deployment nginx-deployment --type=LoadBalancer --name=my-nginx
```
### Vérification
Pour accéder à votre déploiement Nginx, obtenez l'URL du service exposé avec la commande suivante :

```bash
minikube service nginx-deployment --url
```

- Ouvrez votre navigateur et accédez à l'URL affichée pour visualiser la page d'accueil de Nginx.

## Conclusion
Vous avez maintenant déployé 4 instances Nginx sur un cluster Kubernetes géré par Minikube. Ce guide a couvert les étapes de base pour démarrer un cluster, déployer une application et l'exposer à l'extérieur du cluster. 

