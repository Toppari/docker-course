```console
$ docker build -t example-backend:1.14 .
Sending build context to Docker daemon   42.5kB
Step 1/9 : FROM golang:1.16
 ---> 972d8c0bc0fc
Step 2/9 : EXPOSE 8080
 ---> Using cache
 ---> b26935be9c0f
Step 3/9 : ENV REQUEST_ORIGIN=http://localhost:5000
 ---> Running in 4755d113df85
Removing intermediate container 4755d113df85
 ---> c0283f8b6c80
Step 4/9 : WORKDIR /usr/src/app
 ---> Running in 77d8694f8277
Removing intermediate container 77d8694f8277
 ---> 92e804d7c948
Step 5/9 : COPY go.mod go.sum ./
 ---> c79089a9cffd
Step 6/9 : RUN go mod download && go mod verify
 ---> Running in 67392c489f06
all modules verified
Removing intermediate container 67392c489f06
 ---> 8934b0508210
Step 7/9 : COPY . .
 ---> 248115ccfce9
Step 8/9 : RUN REQUEST_ORIGIN=${REQUEST_ORIGIN} go build
...

$ docker run -d -p 8080:8080 --name backend example-backend:1.14
86da9a15f982ed56fbb4b99713eaf7385319ef1a7caac67cab8f4ec74d46caf3
```
