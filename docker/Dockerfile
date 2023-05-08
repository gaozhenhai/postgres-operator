FROM alpine:3.16
MAINTAINER Zhenhai Gao <gaozh1988@live.com>

ENV TZ="Asia/Shanghai"

COPY build/* /
RUN apk --no-cache add curl ca-certificates tzdata && \
    addgroup -g 1000 pgo && \
    adduser -D -u 1000 -G pgo -g 'Postgres Operator' pgo

USER 1000:1000
ENTRYPOINT ["/postgres-operator"]
