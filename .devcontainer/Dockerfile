FROM debian:bookworm-slim@sha256:88200866dfff7ea7f5cbcb6ec7c8a701889efe6fe859fe64d6990e4b07ea4171

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install --yes --no-install-recommends \
        ca-certificates \
        curl \
        git \
        procps \
        sudo \
    && groupadd --gid 1000 repro \
    && useradd --uid 1000 --gid 1000 --create-home --shell /bin/bash repro \
    && echo "repro ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/repro \
    && chmod 0440 /etc/sudoers.d/repro \
    && rm -rf /var/lib/apt/lists/*

USER root
