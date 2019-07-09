FROM golang:alpine as builder

WORKDIR /app
COPY main.go .

RUN go build -o main .

RUN chmod +x main.go

FROM scratch
WORKDIR /app
COPY --from=builder /app/ /app/

CMD ["./main"]