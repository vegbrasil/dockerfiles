FROM alpine:3.8

ENV HUGO_VERSION 0.47.1

RUN apk add --update wget

RUN wget https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_${HUGO_VERSION}_Linux-64bit.tar.gz

RUN tar xzf hugo_${HUGO_VERSION}_Linux-64bit.tar.gz && \
    mv hugo /usr/bin/

RUN rm hugo_${HUGO_VERSION}_Linux-64bit.tar.gz LICENSE README.md && \
    apk del wget && \
    rm -r /var/cache/apk

VOLUME ["/app"]

WORKDIR /app

ENTRYPOINT ["/usr/bin/hugo"]