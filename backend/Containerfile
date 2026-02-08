
#Stage 1.
FROM golang:1.24-alpine AS builder 

WORKDIR /app

COPY . .

RUN go build -o guestbook-api .

#Stage 2.
FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/guestbook-api .

EXPOSE 5000
USER 1000:1000

CMD ["./guestbook-api"]
