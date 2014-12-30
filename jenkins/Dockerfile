FROM ubuntu:trusty
MAINTAINER Stanley Ng "stanleyhlng@yahoo.com.hk"
ENV REFRESHED_AT 2014-12-29

RUN apt-get update -qq && apt-get install -qqy curl
RUN curl https://get.docker.io/gpg | apt-key add -
RUN echo deb http://get.docker.io/ubuntu docker main > /etc/apt/sources.list.d/docker.list
RUN apt-get update -qq && apt-get install -qqy iptables ca-certificates lxc openjdk-6-jdk git-core lxc-docker
RUN apt-get install -y git

# Fixes empty home
ENV HOME /root
# add custom ssh config / keys to the root user
ADD ssh/ /root/.ssh/
# Fixes permission if needed
RUN chmod 600 /root/.ssh/*

# Avoid first connection host confirmation
RUN ssh-keyscan -p2200 github.com > /root/.ssh/known_hosts

ENV JENKINS_HOME /opt/jenkins/data
ENV JENKINS_MIRROR http://mirrors.jenkins-ci.org

RUN mkdir -p $JENKINS_HOME/plugins
RUN curl -sf -o /opt/jenkins/jenkins.war -L $JENKINS_MIRROR/war-stable/latest/jenkins.war

RUN for plugin in chucknorris greenballs scm-api git-client git ws-cleanup ;\
	do curl -sf -o $JENKINS_HOME/plugins/${plugin}.hpi \
		-L $JENKINS_MIRROR/plugins/${plugin}/latest/${plugin}.hpi; done

ADD ./jenkins.sh /usr/local/bin/jenkins.sh
RUN chmod +x /usr/local/bin/jenkins.sh

VOLUME /var/lib/docker

EXPOSE 8080

ENTRYPOINT [ "/usr/local/bin/jenkins.sh" ]
