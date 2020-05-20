FROM rust:slim

USER root
# install python
RUN apt-get update
RUN apt-get install -y python3
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 1 \
    && python --version

RUN git clone -b exp https://github.com/maxtnuk/deno.git
RUN cd deno
RUN git submodule update --init

RUN cd cli && cargo install --path .

WORKDIR /workspace

ENV DENO_INSTALL="/root/.deno"
