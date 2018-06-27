FROM alpine:latest

RUN apk update && \
    apk --no-cache add php7 php7-json php7-mbstring php7-ctype php7-openssl php7-pdo php7-tokenizer php7-xml tar nodejs yarn && \
    apk add mysql mysql-client && \
    addgroup mysql mysql && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    mkdir /scripts && \
    rm -rf /var/cache/apk/*

VOLUME ["/var/lib/mysql"]

COPY ./startup.sh /scripts/startup.sh
RUN chmod +x /scripts/startup.sh

EXPOSE 3306

ENTRYPOINT ["/scripts/startup.sh"]
