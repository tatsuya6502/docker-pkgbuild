FROM centos:centos7

RUN (yum -y update && \
     yum -y install \
         asciidoc \
         curl \
         git \
         make \
         python2-devel \
         rpm-build \
         sudo \
         && \
     yum clean all && \
     groupadd sudo && \
     groupadd builder --gid 5000 && \
     useradd builder --gid 5000 --create-home --shell /bin/bash --groups sudo)

# Allow sudo without a password.
ADD sudoers /etc/sudoers.d/nopasswd

USER builder
RUN mkdir -p /home/builder/src

# Expect our source code to live in /home/builder/src. We will run
# the build as user `builder` with group `builder` (gid: 5000).

WORKDIR /home/builder/src
