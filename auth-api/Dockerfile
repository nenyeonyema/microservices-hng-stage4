FROM golang:1.21 AS build
WORKDIR /app
COPY . .
RUN go mod tidy && go build -o auth

FROM alpine:latest
WORKDIR /root/
COPY --from=build /app/auth .
CMD ["./auth"]

