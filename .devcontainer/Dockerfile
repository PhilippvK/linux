# [Choice] Ubuntu version: bionic, focal
ARG VARIANT=focal
FROM mcr.microsoft.com/vscode/devcontainers/base:${VARIANT}

# Install required dependencies and toolchain
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends bc bison flex libssl-dev make libc6-dev libncurses5-dev 

# Install the 64-bit toolchain for a 64-bit kernel
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends crossbuild-essential-arm64

# Install checkpatch.pl
RUN wget -O /usr/local/bin/checkpatch.pl https://raw.githubusercontent.com/raspberrypi/linux/rpi-5.4.y/scripts/checkpatch.pl
