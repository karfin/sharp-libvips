FROM debian:wheezy
MAINTAINER Lovell Fuller <npm@lovell.info>

# Create Debian-based container suitable for building Linux x64 binaries

# Build dependencies
RUN \
  echo "deb http://ftp.debian.org/debian wheezy-backports main" | tee /etc/apt/sources.list.d/wheezy-backports.list && \
  apt-get update && \
  apt-get install -y build-essential autoconf libtool nasm gtk-doc-tools texinfo gperf advancecomp && \
  apt-get -t wheezy-backports install -y jq && \
  curl https://sh.rustup.rs -sSf | sh -s -- -y

# Compiler settings
ENV \
  PATH="/root/.cargo/bin:$PATH" \
  PLATFORM="linux-x64" \
  FLAGS="-O3"
