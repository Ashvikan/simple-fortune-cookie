FROM golang:latest AS build

COPY ./ /app
WORKDIR /app

RUN go mod download
RUN go build

FROM golang:1.19.0-alpine

LABEL rg.opencontainers.image.source "https://github.com/Ashvikan/simple-fortune-cookie"
COPY --from=build /app /app
WORKDIR /app

ENTRYPOINT ["go", "run"]
CMD ["main.go"]