FROM php:7.2.6-fpm-alpine3.7

RUN docker-php-ext-install pdo pdo_mysql && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    apk update && \
    apk --no-cache add tar nodejs yarn && \
    apk add mysql mysql-client && \
    addgroup mysql mysql && \
    mkdir /scripts && \
    rm -rf /var/cache/apk/*

COPY ./startup.sh /scripts/startup.sh
RUN chmod +x /scripts/startup.sh

EXPOSE 3306

ENTRYPOINT ["/scripts/startup.sh"]