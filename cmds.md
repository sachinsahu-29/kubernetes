# create a cluster
kind create cluster --name cka-cluster1  

kind create cluster --name cka-cluster2 --config pod.yaml

# get cluster
kind get clusters

# get details for particular cluster
kind cluster-info --context kind-cka-cluster1

# to get nodes present in cluster
kubectl get nodes

# show running clusters
kubectl config get-contexts

# switch to a cluster
kubectl config use-context kind-cka-cluster1

# create pod in current cluster
kubectl run nginx-pod --image=nginx:latest

# create pod with yaml file
kubectl create -f pod.yaml

# creates or updates Kubernetes resources from a YAML file.
kubectl apply -f pod.yaml

# shows all pods in the current namespace across all nodes in the cluster.
kubectl get pods

# To see which node a pod is running on
kubectl get pods -o wide

# Used to learn what fields a resource supports.
kubectl explain pod

# Used to inspect a real object running in the cluster
kubectl describe pod nginx-pod

# delete a pod 
kubectl delete pod nginx-pod

# get all namespace
kubectl get namespace    

kubectl get ns    

# create namespace
kubectl create ns ngnix 

# get inside pod
kubectl exec -it nginx-pod -- sh

exit

# scale the deployment
kubectl scale deploymentnginx-deployment -n nginx --replicas=5       

# change version
kubectl set image deployment/nginx-deployment -n nginx nginx=nginx:1.27.3

# Watch the rollout
kubectl rollout status deployment/nginx-deployment -n nginx

# roll-back
kubectl rollout undo deployment/nginx-deployment -n nginx