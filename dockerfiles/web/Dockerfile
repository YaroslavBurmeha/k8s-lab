FROM alpine:3.19
RUN apk update && apk upgrade && apk add --no-cache nginx php7-fpm && rc-update add nginx default
COPY app-code/. /var/www/html/
COPY . /etc/nginx/
