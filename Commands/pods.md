### Commands on pods

kubectl get pods -> To see existing pods

kubectl run nginx --image=nginx --> To create a image in name "nginx"

kubectl describe pod name -->To see details of a particular pod

kubectl get pods -o wide --> to see details in pod

kubectl delete pod name --> To delete a pod

## To create a new pod and image 
kubectl run redis --image=redis123 --dry-run -o yaml 


kubectl run redis --image=redis123 --dry-run=client -o yaml

## To create and run a yaml file
kubectl run redis --image=redis123 --dry-run=client -o yaml > redis.yaml

example:-

kubectl create -f redis.yaml

kubectl apply -f redis.yaml