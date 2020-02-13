FROM golang:1.7.3 AS builder
WORKDIR /go/src/app
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM scratch

WORKDIR /go/src/app
COPY --from=0 /go/src/app .
CMD ["./app"]