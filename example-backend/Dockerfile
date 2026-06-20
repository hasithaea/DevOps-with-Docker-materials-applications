FROM golang:1.23-alpine AS builder

WORKDIR /myapp

COPY . .

RUN go build -o server .

FROM scratch

WORKDIR /myapp

COPY --from=builder /myapp/server .

ENV PORT=8080 \
    REQUEST_ORIGIN=http://localhost:5001

EXPOSE 8080

CMD [ "./server" ]