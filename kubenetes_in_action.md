docker run busybox echo "Hello world"
docker run <image>:<tag>

docker build -t kubia .

docker image

docker run --name kubia-container -p 8080:8080 -d kubia

docker ps

docker inspect kubia-container

docker exec -it kubia-container bash