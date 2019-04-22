FROM alpine:3.9

RUN apk upgrade --update --no-cache && \
    apk add ca-certificates && \
    update-ca-certificates

# Adding ipa.os4-sandbox.paas.redhat.com cert
COPY build/ipa-cert.crt /usr/local/share/ca-certificates/ipa-cert.crt
RUN update-ca-certificates

USER nobody

ADD build/_output/bin/ipa-cert-operator /usr/local/bin/ipa-cert-operator
