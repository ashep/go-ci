ARG ARCH
FROM --platform=linux/${ARCH} alpine:latest

ARG APP_NAME
ARG APP_VERSION

RUN mkdir -p build && \
    go mod vendor && \
    go build -ldflags="-X 'github.com/ashep/go-apprun.appName=${APP_NAME}' -X 'github.com/ashep/go-apprun.appVer=${APP_VERSION}'" -o build/app main.go

COPY ./build/app /app/app
ENTRYPOINT ["/app/app"]
