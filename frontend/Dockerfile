FROM golang:1.17.0-alpine as builder
WORKDIR /go/src
COPY ./ ./
RUN go mod tidy && go build


# FROM alpine:latest
FROM alpine:latest
COPY --from=builder /go/src ./
ENTRYPOINT ["./frontend"]
