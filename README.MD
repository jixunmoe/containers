# Containers

## `debian-packaging-crosscompile`

[![Debian: Package CrossCompile](https://github.com/jixunmoe/containers/actions/workflows/debian-packaging-crosscompile.yml/badge.svg)](https://github.com/jixunmoe/containers/actions/workflows/debian-packaging-crosscompile.yml)

```sh
docker pull ghcr.io/jixunmoe/debian-packaging-crosscompile:main
```

Container setup to perform cross-compilation and Debian packaging for
`armel` and `armhf`.

## Dokuwiki

[![Debian: Package CrossCompile](https://github.com/jixunmoe/containers/actions/workflows/debian-packaging-crosscompile.yml/badge.svg)](https://github.com/jixunmoe/containers/actions/workflows/debian-packaging-crosscompile.yml)

```sh
docker pull ghcr.io/jixunmoe/dokuwiki:stable_2020-07-29
```

Mount a the whole app directory for data preservation.

It will be upgraded on container startup.

```sh
docker run --rm -it -p 127.0.0.1:80:80 -v "$PWD":/app \
    ghcr.io/jixunmoe/dokuwiki:stable_2020-07-29
```

Put the container behind a reverse proxy and set `X-Real-IP`, e.g.:

```
proxy_set_header X-Real-IP $remote_addr;
proxy_pass http://dokuwiki_internal;
```

You can also add custom init scripts to `/init.d/*.sh`.
