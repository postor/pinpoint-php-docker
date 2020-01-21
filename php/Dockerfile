FROM php:7.4.1-fpm-alpine3.11

WORKDIR /root

RUN apk add --no-cache git autoconf g++ make python3 python3-dev linux-headers file

RUN git clone https://github.com/naver/pinpoint-c-agent.git

WORKDIR /root/pinpoint-c-agent/PHP/pinpoint_php_ext

RUN set -x \\
  && phpize && ./configure && make && make install

WORKDIR /root/pinpoint-c-agent/PHP/collector-agent

RUN pip3 install -r requirements.txt 

WORKDIR /var/www/html