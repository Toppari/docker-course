```console
$ docker image pull devopsdockeruh/simple-web-service:alpine
alpine: Pulling from devopsdockeruh/simple-web-service
ba3557a56b15: Pull complete
1dace236434b: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:dd4d367476f86b7d7579d3379fe446ae5dfce25480903fb0966fc2e5257e0543
Status: Downloaded newer image for devopsdockeruh/simple-web-service:alpine
docker.io/devopsdockeruh/simple-web-service:alpine
$ docker images
REPOSITORY                          TAG       IMAGE ID       CREATED         SIZE
ubuntu                              latest    27941809078c   5 weeks ago     77.8MB
devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   16 months ago   83MB
devopsdockeruh/simple-web-service   alpine    fd312adc88e0   16 months ago   15.7MB
$ docker run -d --name alpine devopsdockeruh/simple-web-service:alpine
f57ae3b9aee4a9d8d219135ca1771a54fa0c39ca6a34f83472f77b280f36111d
$ docker exec -it alpine sh
/usr/src/app # tail -f ./text.log
2022-07-17 14:17:16 +0000 UTC
2022-07-17 14:17:18 +0000 UTC
2022-07-17 14:17:20 +0000 UTC
2022-07-17 14:17:22 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```
