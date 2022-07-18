FROM golang:1.16

EXPOSE 8080

ENV REQUEST_ORIGIN=http://localhost:5000

WORKDIR /usr/src/app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
COPY go.mod go.sum ./
RUN go mod download && go mod verify

COPY . .
RUN REQUEST_ORIGIN=${REQUEST_ORIGIN} go build

CMD ["./server"]