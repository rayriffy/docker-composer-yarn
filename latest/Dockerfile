FROM alpine:latest

RUN apk update && \
    apk --update add wget \ 
    	curl \
    	git \
    	php7 \
    	php7-curl \
    	php7-openssl \
    	php7-iconv \
        php7-xml \
        php7-pdo \
        php7-tokenizer \
        php7-xmlwriter \
    	php7-json \
    	php7-mbstring \
    	php7-phar \
    	php7-dom --repository http://nl.alpinelinux.org/alpine/edge/testing/ && rm /var/cache/apk/* && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    apk --no-cache add tar nodejs yarn && \
    apk update && \
    apk add mysql mysql-client libpng-dev gcc make alpine-sdk && \
    addgroup mysql mysql && \
    mkdir /scripts && \
    apk add --update \
    bash \
    lcms2-dev \
    libpng-dev \
    gcc \
    g++ \
    make \
    autoconf \
    automake && \
    rm -rf /var/cache/apk/*

VOLUME ["/var/lib/mysql"]

COPY ./startup.sh /scripts/startup.sh
RUN chmod +x /scripts/startup.sh

EXPOSE 3306

ENTRYPOINT ["/scripts/startup.sh"]
