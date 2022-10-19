# syntax=docker/dockerfile:1

FROM ubuntu:latest

WORKDIR /

RUN apt update && apt install -y nginx

COPY gunicorn_nginx.conf /etc/nginx/sites-available/gunicorn_nginx.conf

RUN ln -s /etc/nginx/sites-available/gunicorn_nginx.conf /etc/nginx/sites-enabled/gunicorn_nginx.conf

RUN unlink /etc/nginx/sites-enabled/default

EXPOSE 80/tcp
ENV SOCKET_IP="gunicorndjnet:8000"

CMD ["nginx","-g","daemon off;"]