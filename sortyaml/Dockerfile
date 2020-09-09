FROM alpine:3.12

RUN apk add --no-cache ruby ruby-bundler && gem install i18n_yaml_sorter

WORKDIR /tmp

ENTRYPOINT ["sort_yaml"]
