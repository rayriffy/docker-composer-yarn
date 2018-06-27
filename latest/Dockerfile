FROM composer:1.6.5

ENV PATH "$HOME/.yarn/bin:$PATH"
 
RUN apk --no-cache add tar nodejs libpng-dev

RUN rm -rf /root/.yarn && curl -o- -L https://yarnpkg.com/install.sh | bash
