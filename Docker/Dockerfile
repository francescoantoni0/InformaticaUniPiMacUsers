FROM ubuntu:noble

LABEL maintainer="f.antoni1@studenti.unipi.it"
ENV DEBIAN_FRONTEND=noninteractive

# Installo pacchetti potenzialmente utili
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
        openssh-server \
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
        gdb
        
# Installo i pacchetti necessari per assembly AESO

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    dpkg --add-architecture armhf && \
    apt-get update && \
    apt-get install -y \
        gcc-arm-linux-gnueabihf \
        qemu-user \
        gdb-multiarch && \
    rm -rf /var/lib/apt/lists/*

RUN useradd -m user && yes password | passwd user

RUN mkdir -p /run/sshd

WORKDIR /home/user

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
