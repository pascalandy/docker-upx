# docker-upx

A simple little Docker container to build [UPX](https://github.com/upx/upx) and self-minify the binary.

This makes use of [Docker's multi-stage builds](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) (available since `v17.05`).

## Usage

You could run it directly on some mapped volume:

```
docker run --rm -v "$PWD/foo:/foo" devalias/upx:devel --brute -o /foo/bar.upx /foo/bar
```

Or you could copy it into another Dockerfile:

```
FROM devalias/upx:devel AS upx

FROM your/baseimage
COPY --from=upx /usr/bin/upx /usr/bin/upx
```

## GitHub

* https://github.com/0xdevalias/docker-upx

## DockerHub

* https://hub.docker.com/r/devalias/upx/

## Improvements

* ...

## Author

[Glenn 'devalias' Grant](http://devalias.net/) ([@_devalias](https://twitter.com/_devalias))
