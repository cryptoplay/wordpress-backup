ROM alpine:edge
MAINTAINER CryptoPlay <docker@cryptoplay.tk>

RUN apk add --no-cache && \
    mysql-client cron bzip2 && \
    rm -rf /var/cache/apk/* && \
    mkdir /backups

ENV BACKUP_TIME 0 3 * * *

COPY docker-entrypoint.sh /entrypoint.sh
COPY backup restore /bin/

VOLUME /backups

ENTRYPOINT ["/entrypoint.sh"]

CMD ["cron", "-f"]
