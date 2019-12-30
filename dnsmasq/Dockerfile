FROM alpine
# FROM hypriot/rpi-alpine-scratch raspberry piの場合はこちらを使用

RUN apk update && \
    apk upgrade && \
    apk add bash dnsmasq && \
    rm -rf /var/cache/apk/* && \
    mkdir -p /etc/default/ && \
    mkdir -p /var/log/dnsmasq/ && \
    echo -e "ENABLED=1\nIGNORE_RESOLVCONF=yes" > /etc/default/dnsmasq

RUN apk --no-cache add tzdata && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apk del tzdata

CMD ["dnsmasq","--no-daemon"]