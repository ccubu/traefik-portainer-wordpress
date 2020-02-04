ROM debian:latest

EXPOSE 6379

RUN apt -y update
RUN apt-get -y install wget
RUN apt-get -y install build-essential
RUN wget http://download.redis.io/redis-stable.tar.gz
RUN tar xvzf redis-stable.tar.gz
RUN cd redis-stable && make && make install

VOLUME ["/data"]

CMD ["redis-server"]

