# syntax=docker/dockerfile:experimental
FROM aquasec/aqua-scanner:v0.124.3-test-11

RUN mkdir /var/certs
ADD common/ca.crt /var/certs/

# ADD common/ca.crt /etc/ssl/certs/
# ADD common/ca.crt /usr/local/share/ca-certificates/

# RUN apk -U upgrade --no-cache \
#     && apk --no-cache add ca-certificates curl

# RUN update-ca-certificates

ENTRYPOINT ["tail", "-f", "/dev/null"]
