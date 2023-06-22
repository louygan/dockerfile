VERSION?=1.1.1h
REGISTRY?=louygan
PROJECT?=openssl-alpine

build:
        docker build . --build-arg version=${VERSION} -t ${REGISTRY}/${PROJECT}:${VERSION}

push: build
        docker push ${REGISTRY}/${PROJECT}:${VERSION}

clean:
        sudo docker rmi -f ${REGISTRY}/${PROJECT}:${VERSION} || true
[ezganlu@seliiuvd01100 0622-04:14:03 /proj/udm_ccrciv/ezganlu/svn/bin/dockerfile/alpine/openssl/build ]$ cat Dockerfile
### Dockerfile for building latest OpenSSL

# Alpine OS 3.8
# http://dl-cdn.alpinelinux.org/alpine/v3.8/community/x86_64/
FROM alpine:3.10

MAINTAINER Tuan Vo <vohungtuan@gmail.com>


### Some env variables
### I don't know how to get the latest version of OpenSSL, like openssl-latest.tar.gz
### So I have to put the version here
ARG version="1.0.2p"
ENV OPENSSL_VERSION=$version


####################################################
########               GCC   and tools          ###########
####################################################
# The GNU Compiler Collection 5.3.0-r0

RUN set -x \
    && apk add --no-cache \
        bash \
        wget \
        gcc \
        tar \
        alpine-sdk \
        perl \
        linux-headers \
    && rm -rf /var/cache/apk/* \

 ### BUILD OpenSSL
 && wget --no-check-certificate -O /tmp/openssl-${OPENSSL_VERSION}.tar.gz "https://www.openssl.org/source/openssl-${OPENSSL_VERSION}.tar.gz" \
 && tar -xvf /tmp/openssl-${OPENSSL_VERSION}.tar.gz -C /tmp/ \
 && rm -rf /tmp/openssl-${OPENSSL_VERSION}.tar.gz \
 && cd /tmp/openssl-${OPENSSL_VERSION} \
 #&& ./Configure linux-x86_64 shared\
 && ./config no-mdc2 no-idea no-seed \
 && make \
 #&& make test \
 && make install \
 && cd .. \
 && rm -rf openssl-${OPENSSL_VERSION} \

 ### remove tools
 && apk del  gcc alpine-sdk perl linux-headers \
 && rm -rf /usr/local/share /usr/local/include /usr/local/lib/*.a



 ENV PATH /usr/local/ssl/bin:$PATH
 ENV LD_LIBRARY_PATH /usr/local/lib
