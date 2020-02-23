FROM alpine:3.11

ENV SS_SERVER_ADDR=0.0.0.0 \
    SS_SERVER_PORT=8388 \
    SS_PASSWORD=ssp@ss \
    SS_METHOD=aes-256-cfb \
    SS_TIMEOUT=300

RUN sed -i 's/v3.11/edge/g' /etc/apk/repositories

RUN apk add --update --no-cache --update-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/main/ --allow-untrusted libressl3.0-libcrypto libsodium \
    && apk add --no-cache --update-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/testing/ --allow-untrusted shadowsocks-libev

EXPOSE ${SS_SERVER_PORT}/tcp ${SS_SERVER_PORT}/udp

ENTRYPOINT /usr/bin/ss-server -s ${SS_SERVER_ADDR} -p ${SS_SERVER_PORT} -k ${SS_PASSWORD} -m ${SS_METHOD} -t ${SS_TIMEOUT}
