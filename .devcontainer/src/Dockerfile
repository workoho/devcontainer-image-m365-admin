# syntax=docker/dockerfile:1.4

ARG VARIANT="ubuntu"

FROM mcr.microsoft.com/devcontainers/base:${VARIANT}

ARG devcontainercli

COPY meta.env /tmp/scripts/
COPY first-run-notice.txt /tmp/scripts/

RUN \
    if [ -z "$devcontainercli" ] ; then \
        printf "\nERROR: This Dockerfile needs to be built with Visual Studio Code or using the devcontainer-cli !" && exit 1; \
    else \
        printf "devcontainer-cli is detected: $devcontainercli"; \
    fi \
    # Upgrade OS
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
    && apt-get -y upgrade --no-install-recommends \
    # Install common admin command line tools
    && apt-get install -y --no-install-recommends \
        # Networking tools
        dnsutils \
        iputils-arping \
        iputils-ping \
        netcat-openbsd \
        openssh-client \
        # Terminal tools
        command-not-found \
        fzf \
        neovim \
        # screen \
        thefuck \
        # tmux \
    # Move first run notice to right spot
    && mkdir -p "/usr/local/etc/vscode-dev-containers/" \
    && mv -f /tmp/scripts/first-run-notice.txt /usr/local/etc/vscode-dev-containers/ \
    # Move meta.env to right spot
    && mkdir -p "/usr/local/etc/dev-containers/" \
    && mv -f /tmp/scripts/meta.env /usr/local/etc/dev-containers/ \
    # Clean up
    && apt-get autoremove -y && apt-get clean -y && rm -rf /var/lib/apt/lists/* /tmp/scripts
