FROM debian:latest
RUN apt update && apt upgrade && apt install -y nginx php-fpm && service nginx enable
COPY app-code/. /var/www/html/
COPY dockerfiles/web/config/. /etc/nginx/
EXPOSE 80