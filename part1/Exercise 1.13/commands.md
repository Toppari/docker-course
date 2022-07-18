```console
$ docker build -t example-backend .
Sending build context to Docker daemon   42.5kB
Step 1/8 : FROM golang:1.16
1.16: Pulling from library/golang
e4d61adff207: Pull complete
4ff1945c672b: Pull complete
ff5b10aec998: Pull complete
12de8c754e45: Pull complete
8c86ff77a317: Pull complete
0395a1c478ba: Pull complete
245345d44ed8: Pull complete
Digest: sha256:5f6a4662de3efc6d6bb812d02e9de3d8698eea16b8eb7281f03e6f3e8383018e
Status: Downloaded newer image for golang:1.16
 ---> 972d8c0bc0fc
Step 2/8 : EXPOSE 8080
 ---> Running in 082ce0d47e69
Removing intermediate container 082ce0d47e69
 ---> b26935be9c0f
Step 3/8 : WORKDIR /usr/src/app
 ---> Running in 17eb3430665f
Removing intermediate container 17eb3430665f
 ---> 54e38d64fbf6
Step 4/8 : COPY go.mod go.sum ./
 ---> 4f828a8398da
Step 5/8 : RUN go mod download && go mod verify
 ---> Running in 631416e08c5c
all modules verified
Removing intermediate container 631416e08c5c
 ---> a595970d6a9a
Step 6/8 : COPY . .
 ---> e4df7da1d911
Step 7/8 : RUN go build
 ---> Running in 7bf01df08e25
Removing intermediate container 7bf01df08e25
 ---> 50cb77ab81cb
Step 8/8 : CMD ["./server"]
 ---> Running in 891c5c3cf8b7
Removing intermediate container 891c5c3cf8b7
 ---> 6a73399c1d7c
Successfully built 6a73399c1d7c
Successfully tagged example-backend:latest
$ docker run -p 8080:8080 -it --name backend example-backend
[Ex 2.4+] REDIS_HOST env was not passed so redis connection is not initialized
[Ex 2.6+] POSTGRES_HOST env was not passed so postgres connection is not initialized
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:   export GIN_MODE=release
 - using code:  gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /ping                     --> server/router.pingpong (4 handlers)
[GIN-debug] GET    /messages                 --> server/controller.GetMessages (4 handlers)
[GIN-debug] POST   /messages                 --> server/controller.CreateMessage (4 handlers)
[GIN-debug] Listening and serving HTTP on :8080
[GIN] 2022/07/18 - 12:37:51 | 200 |        61.5µs |      172.17.0.1 | GET      "/ping"
```
