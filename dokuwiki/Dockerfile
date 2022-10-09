FROM debian:11.5-slim

# Find the version here:
# https://github.com/splitbrain/dokuwiki/tags
ARG DOKUWIKI_RELEASE=stable_2020-07-29
# https://github.com/splitbrain/dokuwiki/archive/refs/tags/release_stable_2020-07-29.tar.gz


RUN apt-get update && apt-get install -y \
    curl \
    imagemagick \
    nginx \
    php7.4 \
    php-bz2 \
    php-curl \
    php-fpm \
    php-gd \
    php-iconv \
    php-imagick \
    php-intl \
    php-json \
    php-mbstring \
    php-opcache \
    php-readline \
    php-xml \
    php-zip \
    && rm -rf /var/lib/apt/lists/*

# Disable nginx logging
RUN mkdir -p /var/log/nginx \
    && ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

ENV DOKUWIKI_RELEASE=${DOKUWIKI_RELEASE}
RUN mkdir -p "/app" \
    && curl --fail -o/dokuwiki.tar.gz -L \
    "https://github.com/splitbrain/dokuwiki/archive/refs/tags/release_${DOKUWIKI_RELEASE}.tar.gz"

COPY root/ /

ENTRYPOINT [ "/dokuwiki" ]
