FROM library/node:18-bullseye

ENV TZ="Asia/Shangha

ARG DEBIAN_FRONTEND=noninteractive
RUN apt update \
    && apt install -y --no-install-recommends sudo vim \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && echo "node ALL=(ALL) NOPASSWD: ALL" >/etc/sudoers.d/node \
    && chmod 0440 /etc/sudoers.d/node