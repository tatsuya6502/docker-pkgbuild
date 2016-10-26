FROM ubuntu:trusty

RUN (apt-get update && \
     apt-get install -y \
         asciidoc \
         curl \
         git \
         make \
         sudo \
         && \
     apt-get clean && rm -rf /var/lib/apt/lists/* && \
     groupadd builder --gid 5000 && \
     useradd builder --gid 5000 --create-home --shell /bin/bash --groups sudo)

# Allow sudo without a password.
ADD sudoers /etc/sudoers.d/nopasswd

USER builder
RUN mkdir -p /home/builder/src

# Expect our source code to live in /home/builder/src. We will run
# the build as user `builder` with group `builder` (gid: 5000).

WORKDIR /home/builder/src
