FROM golang:1.24.3-alpine3.21

WORKDIR /usr/src/app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
COPY go.mod go.sum ./
RUN go mod download

EXPOSE 8080

COPY . .
RUN go build -v -o /usr/local/bin/app ./...

CMD ["app"]
