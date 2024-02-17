ARG ARCH

FROM --platform=linux/${ARCH} alpine:latest

COPY app.out /app/app
RUN chmod 0755 /app/app

ENTRYPOINT ["/app/app"]
