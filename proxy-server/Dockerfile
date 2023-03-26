# syntax=docker/dockerfile:experimental
FROM alpine:latest

ADD common/glider.conf /etc/glider.conf
RUN mkdir /var/certs

ADD common/ca.crt /var/certs/
ADD common/ca.key /var/certs/

ADD common/ca.crt /etc/ssl/certs/
ADD common/ca.crt /usr/local/share/ca-certificates/

RUN apk -U upgrade --no-cache \
    && apk --no-cache add ca-certificates
RUN update-ca-certificates

ADD https://github.com/nadoo/glider/releases/download/v0.16.3/glider_0.16.3_linux_amd64.tar.gz /tmp/glider.tar.gz
RUN tar -zxvf /tmp/glider.tar.gz -C /tmp
RUN cp /tmp/glider_0.16.3_linux_amd64/glider /usr/local/bin/glider

ENTRYPOINT [ "glider", "-config", "/etc/glider.conf", "--verbose" ]
