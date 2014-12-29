FROM ubuntu:latest
MAINTAINER Stanley Ng "stanleyhlng@yahoo.com.hk"
ENV REFRESHED_AT 2014-12-29
RUN apt-get update
RUN apt-get -y -q install nginx
RUN mkdir -p /var/www/html
ADD nginx/global.conf /etc/nginx/conf.d/
ADD nginx/nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
