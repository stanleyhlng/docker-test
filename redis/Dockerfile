# version: 0.0.1
FROM ubuntu:trusty
MAINTAINER Stanley Ng "stanleyhlng@yahoo.com.hk"
ENV REFRESHED_AT 2014-12-29
RUN apt-get update
RUN apt-get -y install redis-server redis-tools
EXPOSE 6379
ENTRYPOINT [ "/usr/bin/redis-serfver" ]
CMD []
