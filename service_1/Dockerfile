FROM golang:1.21

WORKDIR /app

COPY . .

# Build using GOPATH mode (no go.mod required)
RUN go env -w GO111MODULE=off && go build -o main main.go

EXPOSE 8001

CMD ["./main"]

