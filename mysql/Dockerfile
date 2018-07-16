FROM alpine:3.7

ENV ALPINE_SOURCE=/etc/apk/repositories
COPY ./run.sh /scripts/run.sh

RUN echo -e 'http://mirrors.aliyun.com/alpine/v3.7/main\nhttp://mirrors.aliyun.com/alpine/v3.7/community' > $ALPINE_SOURCE && \
    apk update upgrade && \
    apk add --no-cache mariadb mariadb-client pwgen && \
    mkdir -p /scripts/pre-exec.d && \
    mkdir -p /scripts/pre-init.d && \
    mkdir -p /var/lib/mysql && \
    chmod -R 755 /scripts

EXPOSE 3306
VOLUME ["/var/lib/mysql"]
# VOLUME ["/var/lib/mysql/mysql-bin"]
ENTRYPOINT ["/scripts/run.sh"]