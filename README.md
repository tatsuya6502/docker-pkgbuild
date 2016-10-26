# docker-pkgbuilder

Docker containers for building RPM and Debian packages.

Images can be found at: https://quay.io/repository/cloudian/pkgbuilder
[![Docker Repository on Quay](https://quay.io/repository/cloudian/pkgbuilder/status "Docker Repository on Quay")](https://quay.io/repository/cloudian/pkgbuilder)


## Usage

These are plain Docker images with some basic build tools installed
(e.g. rpm-build for CentOS 7).

Suppose you have Makefile in the current working directory (`$(pwd)`),
try:

```
$ alias rpmbuilder7='docker run -it --rm -v "$(pwd)":/home/pkg/src quay.io/cloudian/pkgbuilder:centos7'
$ rpmbuilder7 make
```

This command assumes that `$(pwd)` is readable and writable by gid
5000.


## Tags and Pre-installed Packages

This branch contains the Dockerfile for **centos7** tag. It has
following packages installed.

**centos7**

- asciidoc
- curl
- git
- make (Gnu Make)
- python2-devel
- rpm-build
- sudo

For other image tags, see the top-level README.md in
[each branch](https://github.com/tatsuya6502/docker-pkgbuilder/branches).
