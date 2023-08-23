## Yolo Orchestration
This project makes use of Kubernetes (K8) to orchestrate and expose the YOLO app on a cluster. YOLO is a client-side and backend application, and this project ensures the app's easy deployment and maintenance using Kubernetes.

### Setup Instructions
Follow the steps below to get started with the YOLO Kubernetes Orchestration:
- Make sure `minikube` and `kubectl` are installed on your local machine. You may use Theser to run Kubernetes clusters locally for testing and development.
- Use `git clone repository-url>` to copy this repository to your local system.
- Launch Minikube on your computer. To launch Minikube, use the following command:
```
minikube start
```
4. Navigate to the cloned repository's client and backend directories.
5. Create the following Kubernetes manifests in each directory (client, backend, and database): 
- Deployment: Set the desired state and the number of replicas for the client, backend, and mongo components. - Service: Create Kubernetes services for the client, backend, and mongo components. 
- Secrets: Configure any environment-specific secrets or configuration needed by the program, as defined in the secret files in the resctive directories.
- PVC (PersistentVolumeClaim): Configure persistent storage for the backend component, if applicable. 
The YAML files for these Kubernetes objects can be created based on the needs of your YOLO app.
6. Use the `kubectl apply` command to apply the Kubernetes manifests. For the mongo database, for example:
```
kubectl apply -f database/mongo-pv.yaml
kubectl apply -f database/mongo-pvc.yaml
kubectl apply -f database/mongo-secrets.yaml
kubectl apply -f database/deployment.yaml
kubectl apply -f database/mongo-service.yaml
```
7. To access the YOLO app, go to the deployment tab in your Kubernetes UI and click on the link. You can also use the following command to get the client service's external IP address:
```
kubectl get services
```

### Technology Used
The project is mainly built using YAML which is used for writing Kubernetes manifests to define the desired state of Kubernetes objects.
