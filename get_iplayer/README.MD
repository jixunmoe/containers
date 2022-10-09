# get_iplayer

Source: https://github.com/get-iplayer/get_iplayer

## Tags

This repo will try to maintain the latest version + nightly (at the time of image built):

- `main` (`nightly`)
- `v3.3.0` (`latest`)

## Usage (Pre-built image)

```sh
alias get_iplayer="mkdir -p downloads \
    && docker run -i --rm --user '$(id -u)' \
        -v \"\$(pwd)/downloads:/downloads\" \
        ghcr.io/jixunmoe/get_iplayer:v3.30 get_iplayer"

get_iplayer --help
```

## Build

`GET_IPLAYER_VERSION` can be `v3.30` (default), or `main` (nightly).

Find version names here: [get_iplayer:tags][gi_tags]

```sh
docker build --build-arg GET_IPLAYER_VERSION=v3.30 -t get_iplayer .
```

## Usage (local image)

```sh
alias get_iplayer="mkdir -p downloads \
    && docker run -i --rm --user '$(id -u)' \
        -v \"\$(pwd)/downloads:/downloads\" \
        get_iplayer get_iplayer"

get_iplayer --help
```

[gi_tags]: https://github.com/get-iplayer/get_iplayer/tags
