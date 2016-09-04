FROM ubuntu:xenial

MAINTAINER David Zhang <crispgm@gmail.com>

RUN mkdir -p /home/runtime/src && mkdir -p /home/runtime/bin
RUN wget http://nginx.org/download/nginx-1.10.1.tar.gz && tar zxvf nginx-1.10.1.tar.gz
RUN wget https://github.com/openresty/headers-more-nginx-module/archive/v0.30.tar.gz && tar zxvf v0.30.tar.gz
RUN cd /home/runtime/src/nginx-1.10.1
RUN ./configure --prefix=/home/runtime/bin/nginx --add-module=/home/runtime/src/headers-more-nginx-module-0.30 --with-http_ssl_module --with-http_v2_module \
    && make
    && make install
RUN cd /home/runtime/bin/nginx

EXPOSE 80
ENTRYPOINT ["./sbin/nginx"]
