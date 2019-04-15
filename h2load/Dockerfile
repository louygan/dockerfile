FROM alpine:3.7
RUN \
 NGHTTP2_VERSION='1.33.0' \
 BUILD_DEPS='wget libc-dev gcc g++ make openssl-dev libev-dev zlib-dev jansson-dev libxml2-dev jemalloc-dev c-ares-dev' \
 RUN_DEPS='ca-certificates libstdc++ openssl libev zlib jansson libxml2 jemalloc c-ares' \
 && apk --no-cache add $BUILD_DEPS $RUN_DEPS \
 && cd /tmp \
 && wget -qO- "https://github.com/tatsuhiro-t/nghttp2/releases/download/v${NGHTTP2_VERSION}/nghttp2-${NGHTTP2_VERSION}.tar.gz" | tar -xz \
 && cd /tmp/nghttp2-$NGHTTP2_VERSION \
 && ./configure --enable-app \
 && make \
 && make install-strip \
 && apk del $BUILD_DEPS \
 && rm -rf /tmp/*
ENTRYPOINT ["/usr/local/bin/h2load"]
