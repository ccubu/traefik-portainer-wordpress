FROM debian:latest

ENV DEBIAN_FRONTEND noninteractive

RUN set -eux; \ 
    apt -y update; \
    apt-get -y install wget build-essential; \
    cd /tmp; \ 
    wget http://download.redis.io/redis-stable.tar.gz; \
    tar xvzf redis-stable.tar.gz; \
    cd redis-stable; \
    make; \
    make install; \
    rm -rf /tmp/*; \
    rm -rf /var/lib/apt/lists/*;

VOLUME ["/data"]

WORKDIR /data

EXPOSE 6379

CMD ["redis-server"]

