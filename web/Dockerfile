FROM caddy:2-alpine

ENV DOCKERIZE_VERSION=v0.15.1
RUN apk update --no-cache \
    && wget -O - https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz | tar xzf - -C /usr/local/bin

# Rootless
# RUN addgroup -S caddygroup && adduser -S caddyuser -G caddygroup
# RUN chown -R caddyuser:caddygroup /config /data /etc/caddy /usr/share/caddy
# RUN sed -i 's/:80 {/:8080 {/' /etc/caddy/Caddyfile
# USER caddyuser

CMD ["caddy", "run", "--config", "/etc/caddy/Caddyfile", "--adapter", "caddyfile"]
