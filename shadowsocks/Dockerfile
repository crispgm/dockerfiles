FROM ubuntu:xenial

MAINTAINER David Zhang <crispgm@gmail.com>

RUN apt-get update \
    && apt-get install -y python-pip \
    && pip install shadowsocks

COPY etc/shadowsocks.json /etc/shadowsocks.json

EXPOSE 2968
CMD /usr/local/bin/ssserver -c /etc/shadowsocks.json -d start
