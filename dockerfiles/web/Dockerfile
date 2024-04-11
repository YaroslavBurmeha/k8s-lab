FROM alpine:3.19
RUN apk update && apk upgrade && apk add --no-cache nginx
COPY app-code/. /var/www/html/
COPY . /etc/nginx/
