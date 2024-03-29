# Kubernetes Development Environment

1. Create volume directories:

```
sudo mkdir -p /Volumes/Kubernetes
sudo mkdir /Volumes/Kubernetes/redis
sudo mkdir /Volumes/Kubernetes/postgres
sudo mkdir /Volumes/Kubernetes/elasticsearch
sudo mkdir /Volumes/Kubernetes/kafka

sudo chmod 777 /Volumes/Kubernetes/*
```

2. Apply all services:

```
kubectl apply -f cache
kubectl apply -f cron
kubectl apply -f database
kubectl apply -f elasticstack
kubectl apply -f kafka
kubectl apply -f metrics-server
kubectl apply -f monitoring
```

## Commands

Most used commands for checking the services

1. Check the status of the pods in a given namespace:

   `kubectl get pods -n <namespace>`

2. Get all details of a pod:

   `kubectl describe pods <service> -n <namespace>`

3. Get logs of a pod:

   `kubectl logs -f <pod name> -n <namespace>`

### Cleanup

To remove all services, run the following commands:

```
kubectl delete -f cache
kubectl delete -f database
kubectl delete -f elasticstack
kubectl delete -f kafka
kubectl delete -f metrics-server
kubectl delete -f monitoring
```
