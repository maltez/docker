FROM alpine:3.10.1
MAINTAINER vbakin12@gmail.com

LABEL maintainer=vbakin12@gmail.com
RUN apk add  --no-cache nginx \
&& adduser -D -u 1000 -g 'www' www \
&& mkdir -p /run/nginx

CMD ["nginx", "-g", "daemon off;"]
EXPOSE 80
