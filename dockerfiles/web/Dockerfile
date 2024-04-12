FROM debian:latest
RUN apt update && apt upgrade && apt install --no-cache nginx php-fpm
COPY app-code/. /var/www/html/
COPY . /etc/nginx/
