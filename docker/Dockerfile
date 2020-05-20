FROM rust:slim

USER root
# install python

WORKDIR /workspace

RUN apt-get update
RUN apt-get install -y python3 git
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 1 \
    && python --version

RUN git clone -b exp https://github.com/maxtnuk/deno.git
RUN cd deno && git submodule update --init
RUN cd deno/cli && cargo install --path .

ENV DENO_INSTALL="/root/.deno"
