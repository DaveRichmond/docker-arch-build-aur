[![CI](https://github.com/daverichmond/docker-arch-build-aur/actions/workflows/ci.yml/badge.svg)](https://github.com/daverichmond/docker-arch-build-aur/actions/workflows/ci.yml)

This fork enables building of arm images

### Build AUR packages

The following command will download AUR package and build it:

```
$ docker pull quay.io/daverichmond/arch-build-aur
$ docker run --rm -v $(pwd):/pkg uay.io/daverichmond/arch-build-aur /bin/bash -c '/build-aur <package>'
```

### Build repo packages

The following command will download repo package and build it:

```
$ docker pull quay.io/daverichmond/arch-build-aur
$ docker run --rm -v $(pwd):/pkg quay.io/daverichmond/arch-build-aur /bin/bash -c '/build-repo <package>'
```

### Build PKGBUILD

The following command will build local PKGBUILD file (must reside in a folder mounted to /build):

```
$ docker pull quay.io/daverichmond/arch-build-aur
$ docker run --rm -v $(pwd):/pkg -v $(pwd):/build quay.io/daverichmond/arch-build-aur /bin/bash -c '/build-pkgbuild'
```

`.SRCINFO` file will be updated/created in /build directory.

### Compiled package location

The binary will be placed in the /pkg folder, which in the example above is mounted to the current directory on the host.

---

- Based on [archlinux](https://hub.docker.com/r/archlinux) image.
- Updated daily with [GitHub actions](https://github.com/valdar/docker-arch-build-aur/actions).
- Sources are on [Github](https://github.com/valdar/docker-arch-build-aur).
