FROM debian:latest
RUN apt update && apt install -y nginx php8.2-fpm
COPY app-code/. /var/www/html/
COPY dockerfiles/web/config/. /etc/nginx/
EXPOSE 80
CMD ["nginx","-g","daemon off;"]