FROM debian:11.1-slim

RUN apt-get -qq update \
    && apt-get -yqq -o=Dpkg::Use-Pty=0 --no-install-recommends install \
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

RUN groupadd -g 800 jenkins \
    && useradd -m -g 800 -u 800 jenkins

USER jenkins

CMD [ "/bin/sh" ]
