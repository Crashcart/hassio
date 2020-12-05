ARG BUILD_FROM=hassioaddons/base:8.0.6
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Add env
#ENV TERM="xterm-256color"

# Copy Python requirements file
#COPY requirements.txt /tmp/

# Setup base
ARG BUILD_ARCH=amd64
# hadolint ignore=DL3003
RUN apk add --no-cache \
    coreutils=8.32-r0 \
    wget=1.20.3-r1 \
    cifs-tools 
    
# Copy root filesystem
COPY rootfs /

# Build arguments
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="cifs for hassio" \
    io.hass.description="cifs for hassio to mount windows shares" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Sid Lucas <sid.lucas@gmail.com>" \
    org.opencontainers.image.title="cifs" \
    org.opencontainers.image.description="cifs to add windows mounts to your Home Assistant instance" \
    org.opencontainers.image.vendor="Sid's Add-ons" \
    org.opencontainers.image.authors="Sid Lucas <sid.lucas@gmail.com>" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://place.holder" \
    org.opencontainers.image.source="https://github.com/bla/bla" \
    org.opencontainers.image.documentation="https://github.com/bla/bla/blob/master/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
