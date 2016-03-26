FROM armhf/alpine:latest
MAINTAINER Robert Brown - https://github.com/rjbrown99

# Derived from: https://github.com/kost/docker-alpine/tree/master/alpine-mariadb

RUN apk --update add mysql mysql-client pwgen && \
rm -f /var/cache/apk/* && \
echo "Success"

ADD scripts/run.sh /scripts/run.sh
RUN mkdir /scripts/pre-exec.d && \
mkdir /scripts/pre-init.d && \
chmod -R 755 /scripts

EXPOSE 3306
# WORKDIR /app

VOLUME ["/var/lib/mysql"]

ENTRYPOINT ["/scripts/run.sh"]
