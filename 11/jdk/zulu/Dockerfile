FROM azul/zulu-openjdk-alpine:11.0.5
MAINTAINER Forest Keepers <Jeroen.knoops@philips.com>

RUN apk --no-cache add \
      curl \
      jq \
      git \
      wget \
      openssl \
      bash \
      netcat-openbsd \
      net-tools && \
    rm -rf /var/cache/apk/*

RUN addgroup -S java && \
  adduser -S -G java java

RUN mkdir /app
RUN chown java:java /app

WORKDIR /app

ADD REPO .
ADD TAGS .

ENV JAVA_TOOL_OPTIONS="-XX:+UseContainerSupport"
