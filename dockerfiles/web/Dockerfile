FROM debian:latest
RUN apt update && apt install -y nginx php-fpm
COPY app-code/. /var/www/html/
COPY dockerfiles/web/config/. /etc/nginx/
EXPOSE 80
ENTRYPOINT ["service", "nginx", "start"]