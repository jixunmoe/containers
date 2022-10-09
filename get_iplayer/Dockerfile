FROM debian:11.5-slim

WORKDIR /downloads
ENV HOME=/downloads

RUN apt-get update \
    && apt-get install -y \
    atomicparsley \
    curl \
    ffmpeg \
    libcgi-pm-perl \
    liblwp-protocol-https-perl \
    libmojolicious-perl \
    libwww-perl \
    libxml-libxml-perl \
    && rm -rf /var/lib/apt/lists/*

ARG GET_IPLAYER_VERSION=v3.30

RUN curl -o/usr/local/bin/get_iplayer \
    "https://raw.githubusercontent.com/get-iplayer/get_iplayer/${GET_IPLAYER_VERSION}/get_iplayer" \
    && chmod a+x /usr/local/bin/get_iplayer

CMD [ "get_iplayer" ]
