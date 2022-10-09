FROM debian:11.5-slim

RUN apt-get -qq update \
    && apt-get -yqq -o=Dpkg::Use-Pty=0 --no-install-recommends install \
    \
    build-essential \
    cppcheck \
    \
    debhelper-compat \
    devscripts \
    git \
    \
    binutils-arm-linux-gnueabihf \
    crossbuild-essential-armhf \
    \
    binutils-arm-linux-gnueabi \
    crossbuild-essential-armel \
    \
    binutils-aarch64-linux-gnu \
    crossbuild-essential-arm64 \
    && rm -rf /var/lib/apt/lists/*

CMD [ "/bin/sh" ]
