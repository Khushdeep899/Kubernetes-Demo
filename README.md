# Kubernetes-Demo

K8S-BASICS

K8S-BASICS is a beginner-friendly Kubernetes project that demonstrates the deployment of a simple web application alongside a MongoDB database. The project follows the tutorial from Techworld with Nana on YouTube.

Project Structure

The project includes the following Kubernetes manifest files:

mongo-config.yaml: Configuration file for MongoDB to set up necessary configurations.
mongo-secret.yaml: Secret file for MongoDB to securely store and manage sensitive information such as passwords.
mongo.yaml: Deployment and service definitions for MongoDB.
webapp.yaml: Deployment and service definitions for the web application that interacts with MongoDB.
Prerequisites

To run this project, you need to have the following installed:

Docker
Kubernetes
Minikube (for local deployment)
kubectl (Kubernetes CLI tool)
Getting Started

Follow these steps to get your Kubernetes cluster running with the web application and MongoDB:


Start Minikube with Docker as the driver:
minikube start --driver=docker

Apply the configuration and secret files for MongoDB:
kubectl apply -f mongo-config.yaml
kubectl apply -f mongo-secret.yaml

Deploy MongoDB and the web application:
kubectl apply -f mongo.yaml
kubectl apply -f webapp.yaml

Check the status of your deployments:
kubectl get all

Access the web application by forwarding the service port to your local machine:
kubectl port-forward service/webapp-service 8080:80

Now, the web application should be accessible via http://localhost:8080.


Clean Up

To clean Kubernetes cluster, we can delete the deployments and services:
kubectl delete -f webapp.yaml
kubectl delete -f mongo.yaml<img width="1680" alt="Screenshot 2024-01-30 at 11 46 18 PM" src="https://github.com/Khushdeep899/Kubernetes-Demo/assets/34795705/084e8df7-dd44-4833-b591-0c3584a30207">

kubectl delete -f mongo-config.yaml
kubectl delete -f mongo-secret.yaml


Additionally, you can stop Minikube:
minikube stop

![Uploading Screenshot 2024-01-30 at 11.46.18 PM.png…]()


<img width="1680" alt="Screenshot 2024-01-30 at 11 50 15 PM" src="https://github.com/Khushdeep899/Kubernetes-Demo/assets/34795705/81165899-fe58-4f91-931c-dbacf1ab5152">





