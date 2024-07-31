## Deploy a pod named nginx-pod using the nginx:alpine image.
## Use imperative commands only.

kubectl run nginx-pod --image=nginx:alpine

kubectl run redis --image=redis:alpine --dry-run=client -oyaml > redis-pod.yaml

-----------------
```
---
apiVersion: v1
kind: Pod
metadata:
  labels:
    tier: db
  name: redis
spec:
  containers:
  - image: redis:alpine
    name: redis
  dnsPolicy: ClusterFirst
  restartPolicy: Always
```
------------------------------------
kubectl create -f redis-pod.yaml
------------------------------------
kubectl run redis -l tier=db --image=redis:alpine
--------------------------------------------------

1)Create a service redis-service to expose the redis application within the cluster on port 6379.

kubectl expose pod redis --port=6379 --name redis-service
--------------------------------------------------------------------
kubectl create deployment  webapp --image=kodekloud/webapp-color --replicas=3
------------------------------------------------------------------------
------------------------------------------------------------------------
Create a pod called httpd using the image httpd:alpine in the default namespace. Next, create a service of type ClusterIP by the same name (httpd). The target port for the service should be 80.


Try to do this with as few steps as possible.




'httpd' pod created with the correct image?

'httpd' service is of type 'ClusterIP'?

'httpd' service uses correct target port 80?

'httpd' service exposes the 'httpd' pod?
----------------------------------------------
kubectl run httpd --image=httpd:alpine --port=80 --expose
--------------------------------------------------------

