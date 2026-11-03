# First-party sources only: HashiCorp's official Vault image and Home Assistant's base image.
ARG BUILD_FROM

FROM hashicorp/vault:2.2.1 AS vault

FROM ${BUILD_FROM}

COPY --from=vault /bin/vault /usr/local/bin/vault
COPY rootfs /
RUN chmod a+x /etc/services.d/vault/run /etc/services.d/vault/finish

LABEL io.hass.type="addon"
