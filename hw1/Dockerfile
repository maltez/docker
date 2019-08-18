FROM alpine:3.10.1

LABEL version="1.0.0"
LABEL maintainer="Volodymyr Kaliuzhnyi"

RUN apk update && apk add nginx
RUN mkdir -p /usr/share/www/ /run/nginx/
RUN adduser -D -g 'www' www
RUN mkdir /www
RUN chown -R www:www /var/lib/nginx
RUN chown -R www:www /www

EXPOSE 80

ENTRYPOINT ["/usr/sbin/nginx"]

CMD ["-g", "daemon off;"]
