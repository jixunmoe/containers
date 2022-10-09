# get_iplayer

Source: https://github.com/get-iplayer/get_iplayer

## Build

`GET_IPLAYER_VERSION` can be `v3.30` (default), or `main` (latest).

Find version names here: [get_iplayer:tags][gi_tags]

```sh
docker build --build-arg GET_IPLAYER_VERSION=v3.30 -t get_iplayer .
```

## Use

```sh
alias get_iplayer="mkdir -p downloads \
    && docker run -i --rm --user '$(id -u)' \
        -v \"\$(pwd)/downloads:/downloads\" \
        get_iplayer get_iplayer"

get_iplayer --help
```

[gi_tags]: https://github.com/get-iplayer/get_iplayer/tags
