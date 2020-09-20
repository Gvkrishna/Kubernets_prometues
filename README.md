Create namespace
kubectl apply -f monitoring-namespace.yaml

ConfigMap in Kubernetes provides configuration data to all of the pods in a deployment. 
kubectl apply -f prometheus-config.yaml

Set up a role to give access to all the Kubernetes resources and a service account to apply the role to, both in the monitoring namespace
kubectl apply -f prometheus-roles.yml

Deployment file contains details for a ReplicaSet, including a PodTemplate to apply to all the pods in the set. The ReplicaSet data is contained in the first “spec” section of the file.
kubectl apply -f prometheus-deployment.yaml

Look at the status of the resources in our monitoring namespace
Kubectl get all --namespace=monitoring

To expose the service to external access using NodePort  
kubectl apply -f prometheus-nodeservice.yaml



