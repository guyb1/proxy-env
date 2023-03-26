# syntax=docker/dockerfile:experimental
FROM aquasec/aqua-scanner:latest

RUN mkdir /var/certs
ADD common/ca.crt /var/certs/

# ADD common/ca.crt /etc/ssl/certs/
# ADD common/ca.crt /usr/local/share/ca-certificates/

# RUN apk -U upgrade --no-cache \
#     && apk --no-cache add ca-certificates curl

# RUN update-ca-certificates

ENTRYPOINT ["tail", "-f", "/dev/null"]
