ARG FREEBSD_RELEASE

FROM ghcr.io/freebsd/freebsd-runtime:${FREEBSD_RELEASE}

LABEL org.opencontainers.image.title="FreeBSD base" \
    org.opencontainers.image.description="FreeBSD base image" \
    org.opencontainers.image.authors="Jesús Daniel Colmenares Oviedo <dtxdf@disroot.org>"

ENV ASSUME_ALWAYS_YES=yes

RUN mkdir -p /etc/pkg && \
    printf '%s\n' \
      'FreeBSD-ports-kmods: { enabled: no }' \
      'FreeBSD-base: {' \
      '  url: "pkg+https://pkg.FreeBSD.org/${ABI}/base_release_${VERSION_MINOR}",' \
      '  mirror_type: "srv",' \
      '  signature_type: "fingerprints",' \
      '  fingerprints: "/usr/share/keys/pkgbase-${VERSION_MAJOR}",' \
      '  enabled: yes' \
      '}' \
      'FreeBSD-ports: {' \
      '  url: "pkg+https://pkg.FreeBSD.org/${ABI}/latest",' \
      '  mirror_type: "srv",' \
      '  signature_type: "fingerprints",' \
      '  fingerprints: "/usr/share/keys/pkg",' \
      '  enabled: yes' \
      '}' > /etc/pkg/FreeBSD.conf && \
    rm -rf /usr/local/etc/pkg
