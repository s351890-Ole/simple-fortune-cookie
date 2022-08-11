FROM golang:1.17.0-alpine as builder
COPY . /go/src
RUN cd /go/src && go mod tidy && go build


FROM alpine:latest
COPY --from=builder /go/src/backend /
EXPOSE 9000
ENTRYPOINT ["/backend"]
