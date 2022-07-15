# Commands given

```console
toppari@Toppari-PC:~$ docker container run -d --name secret devopsdockeruh/simple-web-service:ubuntu
toppari@Toppari-PC:~$ docker exec -it secret bash
root@c16eb42fb072:/usr/src/app# tail -f ./text.log
```

# Secret

Secret message is: 'You can find the source code here: https://github.com/docker-hy'
