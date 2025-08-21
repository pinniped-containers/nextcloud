FROM cgr.dev/chainguard/wolfi-base:latest
ARG VERSION=31
WORKDIR /app

LABEL maintainer="Winnie The Pooh winsdominoes@winscloud.net"

RUN apk -U upgrade \
    && rm /var/spool/cron/crontabs \
    && apk add libstdc++ \
    && chown -R nonroot:nonroot /app/ \
    && apk add nextcloud-server \
    && rm -rf /var/cache/apk/*

COPY --from=ghcr.io/pinniped-containers/hardened_malloc:latest /install /usr/local/lib/
ENV LD_PRELOAD="/usr/local/lib/libhardened_malloc.so"
