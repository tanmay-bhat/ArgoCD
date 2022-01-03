FROM golang:1.14 as build
MAINTAINER "tanmay_bhat"
WORKDIR /build
COPY . .
RUN CGO_ENABLED=0 go build -o testapp application/main.go

FROM alpine:3.12
EXPOSE 8080
WORKDIR /app
COPY --from=build /build/testapp .
CMD ["./testapp"]
