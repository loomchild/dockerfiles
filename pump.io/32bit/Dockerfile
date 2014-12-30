#FROM debian:jessie
FROM 32bit/debian:jessie

MAINTAINER Jarek Lipski <loomchild@loomchild.net>

RUN apt-get update \
	&& apt-get install -y nodejs npm graphicsmagick \
	&& rm -rf /var/lib/apt/lists/*

RUN npm install -g databank-mongodb pump.io

RUN ln -s /usr/bin/nodejs /usr/bin/node

RUN groupadd -r pumpio && useradd -r -g pumpio pumpio

RUN mkdir -p /var/local/pump.io/uploads && mkdir -p /var/local/pump.io/logs && chown -R pumpio.pumpio /var/local/pump.io

COPY ../config/pump.io.json /etc/pump.io.json

EXPOSE 31337

VOLUME ["/var/local/pump.io"]

CMD ["pump"]
