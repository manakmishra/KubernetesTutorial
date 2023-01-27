FROM golang:1.16-alpine AS build
WORKDIR /app
COPY go.mod ./
COPY go.sum ./
RUN go mod download
COPY *.go ./
RUN go build -o /app

FROM scratch
COPY --from=build /app /app
EXPOSE 8080 8086 9101
CMD [ "/app" ]