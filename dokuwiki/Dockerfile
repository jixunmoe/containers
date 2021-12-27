FROM debian:11.2-slim

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

RUN mkdir -p "/app" \
    && (curl -o- -L \
    "https://github.com/splitbrain/dokuwiki/archive/refs/tags/release_${DOKUWIKI_RELEASE}.tar.gz" \
    | tar -C "/app" --strip-components=1 -zxvf - ) \
    && chown -R www-data "/app"

COPY root/ /

ENTRYPOINT [ "/dokuwiki" ]
