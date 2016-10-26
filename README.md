# docker-pkgbuild

Docker containers for building RPM and Debian packages.

Images can be found at: https://quay.io/repository/cloudian/pkgbuild
[![Docker Repository on Quay](https://quay.io/repository/cloudian/pkgbuild/status "Docker Repository on Quay")](https://quay.io/repository/cloudian/pkgbuild)


## Usage

These are plain Docker images with some basic build tools installed
(e.g. rpm-build for CentOS 7).

Suppose you have Makefile in the current working directory (`$(pwd)`),
try:

```
$ alias rpmbuilder7='docker run -it --rm -v "$(pwd)":/home/pkg/src quay.io/cloudian/pkgbuild:centos7'
$ rpmbuilder7 make
```

This command assumes that `$(pwd)` is readable and writable by uid
1000 and gid 1000.


## Tags and Pre-installed Packages

See the top-level README.md in [each branch](https://github.com/tatsuya6502/docker-pkgbuild/branches).
