FROM debian:latest
RUN apt update && apt install -y nginx
COPY app-code/. /usr/src/app/
COPY dockerfiles/web/config/. /etc/nginx/
EXPOSE 80
CMD nginx -g "daemon off;"