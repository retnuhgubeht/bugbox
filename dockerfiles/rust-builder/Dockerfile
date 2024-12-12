FROM rust:bullseye

WORKDIR /build

RUN apt update && apt dist-upgrade -y  && DEBIAN_FRONTEND=noninteractive apt install -y \
    ca-certificates \
    binutils \
    help2man \
    make \
    perl \
    git