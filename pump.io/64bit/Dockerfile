FROM debian:jessie

MAINTAINER Jarek Lipski <loomchild@loomchild.net>

RUN apt-get update \
	&& apt-get install -y gcc make build-essential nodejs node-gyp npm graphicsmagick \
	&& rm -rf /var/lib/apt/lists/*

RUN ln -s /usr/bin/nodejs /usr/bin/node

RUN npm install -g databank-mongodb databank-redis databank-memcached pump.io

RUN groupadd -r pumpio && useradd -r -g pumpio pumpio

RUN mkdir -p /var/local/pump.io/uploads && chown -R pumpio.pumpio /var/local/pump.io

COPY pump.io.json /etc/pump.io.json

EXPOSE 31337

VOLUME ["/var/local/pump.io/uploads"]

CMD ["pump"]
