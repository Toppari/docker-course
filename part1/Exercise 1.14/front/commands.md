```console
$ docker build -t example-frontend:1.14 .
Sending build context to Docker daemon  729.1kB
Step 1/8 : FROM node:lts-alpine
 ---> b48aa2e90c0a
Step 2/8 : EXPOSE 5000
 ---> Using cache
 ---> a4a5adbc2fae
Step 3/8 : ENV BACKEND_URL=http://localhost:8080
 ---> Running in e48ae5871b36
Removing intermediate container e48ae5871b36
 ---> 1159ff6a4f20
...

$ docker run -d -p 5000:5000 --name frontend example-frontend:1.14
34babc528ce3430174940a30b0f6aa3c344c2757847da3b6bf2cac325c2598e7
```
