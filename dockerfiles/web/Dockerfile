FROM debian:latest
RUN apt update && apt upgrade && apt install -y nginx php-fpm
COPY app-code/. /var/www/html/
COPY . /etc/nginx/
EXPOSE 80