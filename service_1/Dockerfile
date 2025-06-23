# Stage 1: Build the Go app
FROM golang:1.21 AS builder

WORKDIR /app
COPY . .
RUN go mod init hello && go build -o main .

# Stage 2: Run the Go app
FROM alpine:latest

WORKDIR /app
COPY --from=builder /app/main .

EXPOSE 8001
CMD ["./main"]
