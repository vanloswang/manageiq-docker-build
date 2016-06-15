FROM alpine
MAINTAINER Vanlos Wang vanloswang@126.com

RUN \
  apk --update add ca-certificates ruby ruby-dev ruby-io-console ruby-irb && \
  gem install bundler rake --no-document && \
  rm -rf /var/cache/apk/*

CMD ["irb"]
