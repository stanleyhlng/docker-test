FROM stanleyhlng/redis
MAINTAINER Stanley Ng <stanleyhlng@yahoo.com.hk>
ENV REFRESHED_AT 2015-01-02

ENTRYPOINT [ "redis-server", "--logfile /var/log/redis/redis-replica.log", "--slaveof redis_primary 6379" ]
