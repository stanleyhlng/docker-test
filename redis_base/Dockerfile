FROM ubuntu:14.04
MAINTAINER Stanley Ng <stanleyhlng@yahoo.com.hk>
ENV REFRESHED_AT 2014-12-31

RUN apt-get -yqq update
RUN apt-get install -yqq software-properties-common python-software-properties
RUN add-apt-repository ppa:chris-lea/redis-server
RUN apt-get -yqq update
RUN apt-get -yqq install redis-server redis-tools

VOLUME [ "/var/lib/redis", "/var/log/redis" ]

EXPOSE 6379
CND []
