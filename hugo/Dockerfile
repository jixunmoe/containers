FROM debian:11.5-slim

ARG VER=0.91.2

RUN apt-get update && apt-get install -y \
    wget \
    && (wget -qO- https://github.com/gohugoio/hugo/releases/download/v${VER}/hugo_extended_${VER}_Linux-64bit.tar.gz \
    | tar -C /tmp -zxf -) \
    && mv /tmp/hugo /bin \
    && rm /tmp/* \
    && apt-get -y --autoremove purge wget \
    && rm -rf /var/lib/apt/lists/*
