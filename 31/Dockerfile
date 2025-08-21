ARG VERSION=31

FROM cgr.dev/chainguard/wolfi-base:latest

LABEL maintainer="Winnie The Pooh winsdominoes@winscloud.net"

RUN apk -U upgrade \
    && apk add libstdc++ \
    && apk add nextcloud-server \
    && rm -rf /var/cache/apk/*

COPY --from=ghcr.io/polarix-containers/hardened_malloc:latest /install /usr/local/lib/
ENV LD_PRELOAD="/usr/local/lib/libhardened_malloc.so"
