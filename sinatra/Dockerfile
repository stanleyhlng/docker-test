# version: 0.0.1
FROM ubuntu:trusty
MAINTAINER Stanley Ng "stanleyhlng@yahoo.com.hk"
ENV REFRESHED_AT 2014-12-29

RUN apt-get update
RUN apt-get -y install ruby ruby-dev build-essential redis-tools
RUN gem install --no-rdoc -no-ri sinatra json redis

RUN mkdir -p /opt/webapp

EXPOSE 4567

CMD [ "/opt/webapp/bin/webapp" ]
