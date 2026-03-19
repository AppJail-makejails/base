# FreeBSD

FreeBSD is a free and open-source Unix-like operating system descended from the Berkeley Software Distribution (BSD). The first version was released in 1993 developed from 386BSD, one of the first fully functional and free Unix clones on affordable home-class hardware, and has since continuously been the most commonly used BSD-derived operating system.

wikipedia.org/wiki/FreeBSD

<img src="https://www.freebsd.org/images/banner-red.png" alt="freebsd logo" width="80%" height="auto">

## How to use this Makejail

```sh
appjail makejail -j freebsd -f gh+AppJail-makejails/base -o container="args:--pull"
```

### Arguments

* `base_from` (default: `ghcr.io/appjail-makejails/base`): Location of OCI image. See also [OCI Configuration](#oci-configuration).
* `base_tag` (default: `latest`): OCI image tag. See also [OCI Configuration](#oci-configuration).

## OCI Configuration

```yaml
build:
  variants:
    - tag: 15.0
      containerfile: Containerfile.pkg
      aliases: ["latest"]
      default: true
      args:
        FREEBSD_RELEASE: "15.0"
```
