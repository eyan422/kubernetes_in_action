# Chapter 2

docker run busybox echo "Hello world"
docker run <image>:<tag>

docker build -t kubia .

docker image

docker run --name kubia-container -p 8080:8080 -d kubia

docker ps

docker inspect kubia-container

docker exec -it kubia-container bash

docker stop kubia-container

docker ps -a

docker rm kubia-container

docker tag kubia luksa/kubia

docker login

docker push luksa/kubia

minikube ssh


# Chapter 3

kubectl get nodes

kubectl describe node minikube

kubectl describe node

kubectl get pods

kubectl describe pod pod_name

kubectl expose rc kubia --type=LoadBalancer --name kubia-http

kubectl get services

minikube service kubia-http

kubectl get replicationcontrollers

minikube dashboard

# Chapter 4

kubectl get pod pod_name -o yaml

kubectl explain pods

kubectl explain pod.spec

kubectl create -f kubia-manual.yaml

kubectl get po kubia-manual -o yaml
kubectl get po kubia-manual -o json

kubectl get pods

kubectl create -f kubia-manual-with-labels.yaml
kubectl get po --show-labels
kubectl get po -L creation_method,env

kubectl logs kubia-manual

kubectl logs kubia-manual -c kubia

kubectl port-forward kubia-manual 8888:8080

kubectl label po kubia-manual creation_method=manual

kubectl label po kubia-manual-v2 env=debug --overwrite

kubectl get po -l creation_method=manual --show-labels
kubectl get po -l env --show-labels
kubectl get po -l '!env' --show-labels
kubectl get po -l creation_method!=manual --show-labels
kubectl get po -l 'env in (prod, debug)' --show-labels
kubectl get po -l 'env notin (prod, debug)' --show-labels

kubectl get po -l env=debug,creation_method=manual --show-labels

kubectl label node gke-kubia-85f6-node-0rrx gpu=true
kubectl get nodes -l gpu=true
kubectl get nodes -L gpu

kubectl annotate pod kubia-manual mycompany.com/someannotation="foo bar"

kubectl get ns

kubectl get po --namespace kube-system
kubectl get po -n kube-system

kubectl create -f custom-namespace.yaml
kubectl get ns

kubectl create namespace custom-namespace

kubectl create -f kubia-manual.yaml -n custom-namespace

kubectl config get-contexts

alias kcd='kubectl config set-context $(kubectl config current-context) --namespace '
kcd default

kubectl delete po kubia-gpu

kubectl delete po pod1 pod2

kubectl delete po -l creation_method=manual
kubectl delete po -l rel=canary

kubectl delete ns custom-namespace

kubectl delete po --all

kubectl delete all --all
