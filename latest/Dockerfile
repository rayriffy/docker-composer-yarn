FROM composer:1.6.5

ENV YARN_VERSION 1.7.0

ENV PATH "$HOME/.yarn/bin:$PATH"
 
RUN apk --no-cache add tar nodejs && rm -rf /root/.yarn && touch ~/.bashrc && curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version ${YARN_VERSION}

