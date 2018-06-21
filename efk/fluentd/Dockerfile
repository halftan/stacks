# :vim: ft=dockerfile :
FROM fluent/fluentd:stable

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories \
    && apk add --update --virtual .build-deps sudo \
                                              build-base \
                                              ruby-dev \
    && sudo gem install fluent-plugin-elasticsearch --no-rdoc --no-ri \
    && sudo gem sources --clear-all \
    && apk del .build-deps \
    && rm -rf /var/cache/apk/* \
              /home/fluent/.gem/ruby/2.3.0/cache/*.gem

