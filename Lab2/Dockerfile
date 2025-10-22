FROM ubuntu:noble

LABEL maintainer="f.antoni1@studenti.unipi.it"
ENV DEBIAN_FRONTEND=noninteractive

# Installo pacchetti potenzialmente utili
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
        ssh \
	curl \
        wget \
        git \
        vim \
        nano \
	rsync \
	tar \
	python3 \
        ca-certificates\
        software-properties-common;

# Installo i pacchetti necessari per il corso di lab 2
RUN apt-get install -y \
        build-essential \
        cmake \
        valgrind \
        gdb && \
        rm -rf /var/lib/apt/lists/*

RUN useradd -m user && yes password | passwd user

WORKDIR /app

CMD ["/bin/bash"]
