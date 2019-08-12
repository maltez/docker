FROM alpine:3.10.1

LABEL version="1.0.0"

LABEL maintainer="Sergey.Malovitsa"

RUN apk update && apk add nginx && mkdir /run/nginx && chown nginx:nginx /run/nginx

ENTRYPOINT ["/usr/sbin/nginx"]

CMD ["-g", "daemon off;"]

