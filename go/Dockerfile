ARG ARCH
ARG APP_NAME
ARG APP_VERSION

FROM --platform=linux/${ARCH} golang:1.21-alpine as build

WORKDIR build
COPY . .
RUN go mod vendor && \
    go build -ldflags="-X 'github.com/ashep/go-apprun.appName=${APP_NAME}' -X 'github.com/ashep/go-apprun.appVer=${APP_VERSION}'" -o app.out main.go

FROM --platform=linux/${ARCH} alpine:latest

COPY --from=build /build/app.out /app/app
RUN chmod 0755 /app/app

ENTRYPOINT ["/app/app"]
