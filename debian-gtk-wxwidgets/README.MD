# Debian: GTK3 + wxWidgets

[![Debian: GTK3 + wxWidgets](https://github.com/jixunmoe/containers/actions/workflows/debian-gtk-wxwidgets.yml/badge.svg)](https://github.com/jixunmoe/containers/actions/workflows/debian-gtk-wxwidgets.yml)

This image installs the following dependencies:

- Debian 11.5
    - CMake (+ Make)
    - G++
- wxWidgets (+ gtk 3)
- [linuxdeploy](https://github.com/linuxdeploy/linuxdeploy) (nightly)
  - To create single file `AppImage`.

## Tags

- `main`

## Usage

```dockerfile
FROM ghcr.io/jixunmoe/debian-gtk-wxwidgets:main

WORKDIR /app
COPY . .

# Build your app
RUN ./configure \
    && make -j$(nproc)

# Checkout linuxdeploy guides:
# https://docs.appimage.org/packaging-guide/from-source/linuxdeploy-user-guide.html
RUN linuxdeploy-x86_64.AppImage --plugin gtk --output appimage \
    --appdir Packaging -e Packaging/AppRun

```

## Build

```sh
docker build -t debian-gtk-wxwidgets    \
    --build-arg WXWIDGETS_VERSION=3.1.6 \
    .
```
