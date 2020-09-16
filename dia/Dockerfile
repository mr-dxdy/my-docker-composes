FROM ubuntu:18.04

VOLUME ["${HOME}/Downloads", "${HOME}/Documents", "${HOME}/.dia"]

ENTRYPOINT ["dia"]

RUN apt-get update \
    && apt-get install -y dia \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

