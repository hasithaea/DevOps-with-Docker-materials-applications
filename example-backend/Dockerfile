FROM golang:1.16

WORKDIR /myapp

COPY . .

RUN go build

EXPOSE 8080

RUN go test ./...

CMD [ "./server" ]