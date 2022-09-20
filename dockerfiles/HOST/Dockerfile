FROM ubuntu:20.04
WORKDIR ./

# VOLUME ["./"]
RUN apt-get update -y
RUN apt-get install -y curl build-essential vim

# install rust enviroment
RUN curl https://sh.rustup.rs -sSf | bash -s -- -y
# RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- --default-host=x86_64-unknown-linux-musl -y
RUN echo 'source $HOME/.cargo/env' >> $HOME/.bashrc

# install musl-dev
# RUN apt-get install -y apt-utils
RUN apt-get install -y musl-dev
RUN apt-get install -y musl-tools

RUN echo 'export PS1="🐳 ubuntu \w : "' >> $HOME/.bashrc