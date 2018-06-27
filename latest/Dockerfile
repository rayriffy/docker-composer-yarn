FROM composer:1.6.5

ENV PATH "$HOME/.yarn/bin:$PATH"

RUN apk --no-cache add tar nodejs libpng-dev

RUN rm -rf /root/.yarn && curl -o- -L https://yarnpkg.com/install.sh | bash

RUN apk update && \
	apk add mysql mysql-client && \
	addgroup mysql mysql && \
	mkdir /scripts && \
	rm -rf /var/cache/apk/*

VOLUME ["/var/lib/mysql"]

COPY ./startup.sh /scripts/startup.sh
RUN chmod +x /scripts/startup.sh

EXPOSE 3306

ENTRYPOINT ["/scripts/startup.sh"]
