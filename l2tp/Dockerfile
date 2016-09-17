FROM ubuntu:xenial                                                                                                                                                                

MAINTAINER David Zhang <crispgm@gmail.com>

RUN apt-get update \
    && apt-get install -y wget lsb-release \
    && wget https://git.io/vpnsetup -O vpnsetup.sh

EXPOSE 500/udp 4500/udp

CMD sh vpnsetup.sh && tail -f vpnsetup.sh