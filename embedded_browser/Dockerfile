ARG BUILD_FROM
# hadolint ignore=DL3006
FROM $BUILD_FROM

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN \
    set -x \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        curl \
        iproute2 \
        iputils-ping \
        kmod \
        libcap2-bin \
        libqt5core5a \
        libqt5gui5 \
        libqt5network5 \
        libqt5serialport5 \
        libqt5sql5 \
        libqt5websockets5 \
        libqt5widgets5 \
        libqt5qml5 \
        lsof \
        netcat \
        nginx \
        novnc \
        sqlite3 \
        tigervnc-common \
        tigervnc-standalone-server \
        udev \
        wget \
        wmii \
        xfonts-base \
        xfonts-scalable \
        firefox-esr \
        libssl-dev \
    && rm -rf /var/lib/apt/lists/*

# Copy root filesystem
COPY rootfs /

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="Embedded browser" \
    io.hass.description="Embedded browser inner Home Assistant environment" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Fabio Bigmoby Mauro <https://github.com/bigmoby>" \
    org.opencontainers.image.title="Embedded browser" \
    org.opencontainers.image.description="Embedded browser inner Home Assistant environment" \
    org.opencontainers.image.vendor="Home Assistant Bigmoby Add-ons" \
    org.opencontainers.image.authors="Fabio Bigmoby Mauro <https://github.com/bigmoby>" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://addons.community" \
    org.opencontainers.image.source="https://github.com/bigmoby/addon-embedded-browser" \
    org.opencontainers.image.documentation="https://github.com/bigmoby/addon-embedded-browser/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}
