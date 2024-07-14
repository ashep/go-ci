ARG ARCH

FROM --platform=linux/${ARCH} alpine:latest

COPY app.out /app/app
RUN chmod 0755 /app/app

WORKDIR /app
ENTRYPOINT ["sh", "-c", "env && /app/app"]
