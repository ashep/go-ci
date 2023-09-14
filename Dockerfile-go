ARG ARCH
FROM --platform=linux/${ARCH} alpine:latest

COPY ./build/app /app/app
ENTRYPOINT ["/app/app"]
