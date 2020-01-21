FROM php:7.4.1-fpm-alpine3.11

WORKDIR /root

RUN set -x \\
  && apk add git autoconf g++ make python3 python3-dev linux-headers \\
  && git clone https://github.com/naver/pinpoint-c-agent.git \\
  && cd /root/pinpoint-c-agent/PHP/pinpoint_php_ext \\
  && phpize && ./configure && make && make install \\
  && cd /root/pinpoint-c-agent/PHP/collector-agent \\
  && pip3 install -r requirements.txt 