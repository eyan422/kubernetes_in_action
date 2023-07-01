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