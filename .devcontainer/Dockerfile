FROM ubuntu:24.04

ENV DEVCONTAINER=true

RUN apt-get update && \
    apt-get install -y sudo git curl unzip && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# ubuntuはパスワード無しでsudoが実行できるようにする
RUN echo "ubuntu ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers.d/ubuntu

# ubuntuユーザーに切り替えて作業
USER ubuntu
WORKDIR /home/ubuntu

# Node.jsのインストール
# @see https://nodejs.org/ja/download
RUN curl -o- https://fnm.vercel.app/install | bash
RUN ~/.local/share/fnm/fnm install 22
