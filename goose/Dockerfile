FROM alpine:latest

RUN apk add --no-cache ca-certificates
&& apk add --no-cache --virtual .build-deps build-base git go

ENV GOPATH /go

RUN go get bitbucket.org/liamstask/goose/cmd/goose

RUN cp -pr /go/bin/goose /usr/bin

RUN rm -rf /go \
&& apk del .build-deps

RUN mkdir /db

WORKDIR /db

ENTRYPOINT ["/usr/bin/goose"]
