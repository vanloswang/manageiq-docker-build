FROM alpine
MAINTAINER Vanlos Wang vanloswang@126.com

ENV PATH=$PATH \
    LANG=C.UTF-8 \
    GOSU=https://github.com/tianon/gosu/releases/download/1.9/gosu-amd64 \
    MEMCACHED_DIR=/var/lib/memcached \
    APKINSTALL='bash wget memcached'

RUN adduser -D -h /home/admin -s /bin/bash admin admin && \
    addgroup -S memcached && adduser -S -G memcached memcached && \
    apk add --no-cache ${APKINSTALL} && \
    wget -q --no-check-certificate -O /usr/local/bin/gosu ${GOSU} && \
    chmod +x /usr/local/bin/gosu

COPY memcached.conf /etc/memcached.conf
COPY entrypoint.sh /entrypoint.sh

WORKDIR ${MEMCACHED_DIR}
ENTRYPOINT ["/entrypoint.sh"]
CMD ["memcached"]

EXPOSE 11211
