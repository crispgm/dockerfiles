FROM ubuntu:trusty

MAINTAINER David Zhang <crispgm@gmail.com>

RUN apt-get update && apt-get install -y wget build-essential libpcre3 libpcre3-dev openssl libssl-dev
RUN mkdir -p /runtime
RUN wget http://nginx.org/download/nginx-1.10.1.tar.gz && tar zxvf nginx-1.10.1.tar.gz
RUN wget https://github.com/openresty/headers-more-nginx-module/archive/v0.30.tar.gz && tar zxvf v0.30.tar.gz
RUN cd nginx-1.10.1 && ./configure --prefix=/runtime/nginx \
    --add-module=$(`pwd`)/headers-more-nginx-module-0.30 \
    --with-http_ssl_module --with-http_v2_module \
    && make \
    && make install

VOLUME ["/home", "/nginx_conf", "/etc/letsencrypt/live"]

EXPOSE 80
ENTRYPOINT cd /runtime/nginx && ./sbin/nginx -c /nginx_conf/nginx.conf && tail -f /runtime/nginx/logs/access.log
