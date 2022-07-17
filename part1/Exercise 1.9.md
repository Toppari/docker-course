```console
$ touch text.log
$ docker run -d -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
f4aca9d292b56fde434aced598ad3d338e40ec9024630ce04600055e5d38d0ab
$ tail -f text.log
2022-07-17 15:34:24 +0000 UTC
2022-07-17 15:34:26 +0000 UTC
2022-07-17 15:34:28 +0000 UTC
2022-07-17 15:34:30 +0000 UTC
2022-07-17 15:34:32 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-07-17 15:34:34 +0000 UTC
2022-07-17 15:34:36 +0000 UTC
```
