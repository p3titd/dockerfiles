FROM golang:alpine

RUN apk add --no-cache --virtual .build-deps build-base git \
&& go get bitbucket.org/liamstask/goose/cmd/goose \
&& apk del .build-deps

RUN mkdir /db

WORKDIR /

ENTRYPOINT ["/go/bin/goose"]
