1. Création d'un Namespace :
 
kubectl create --namespace=samira

2. Déploiement de RabbitMQ :
 
kubectl apply -f rabbitmq_cluster_config.yaml --namespace=samira

3. Déploiement de PostgreSQL :
 
kubectl apply -f database_deployment.yaml --namespace=samira

4. Déploiement du Serveur Node.js :
 
kubectl apply -f backend_deployment.yaml --namespace=samira

5. Configuration de l'Autoscaler pour le Serveur :

kubectl autoscale deployment backend_deployment --min=<nombre-minimum-de-replicas> --max=<nombre-maximum-de-replicas> --cpu-percent=<pourcentage-d-utilisation-de-CPU> --namespace=samira

6. Vérification des Ressources Déployées :

kubectl get pods, services, deployments, namespaces --namespace=samira

7. Récupération des Logs d'un Pod :

kubectl logs <nom-du-pod> --namespace=samira

8. Gestion des Ressources avec les Fichiers YAML :

kubectl apply -f backend_autoscaler.yaml
kubectl delete -f backend_autoscaler.yaml
kubectl apply -f backend_autoscaler.yaml