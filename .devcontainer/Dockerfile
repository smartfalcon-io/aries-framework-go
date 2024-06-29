FROM ubuntu:noble

RUN apt update && apt upgrade -y && \
apt install build-essential git wget -qqy 

ARG GO_VERSION=1.22.4

ARG LIBINDY_VDR_VERSION=v0.4.3

RUN wget  https://go.dev/dl/go${GO_VERSION}.linux-amd64.tar.gz && tar -C /usr/local -xzf go${GO_VERSION}.linux-amd64.tar.gz && rm go${GO_VERSION}.linux-amd64.tar.gz

RUN mkdir -p ~/go/bin

ENV GO_BIN=~/go

ENV PATH=$PATH:/usr/local/go/bin:$GO_BIN

RUN wget https://github.com/hyperledger/indy-vdr/releases/download/${LIBINDY_VDR_VERSION}/library-linux-x86_64.tar.gz && tar -C /usr/local/lib -xzf library-linux-x86_64.tar.gz && ldconfig && \
wget https://raw.githubusercontent.com/hyperledger/indy-vdr/${LIBINDY_VDR_VERSION}/libindy_vdr/include/libindy_vdr.h -O /usr/include/libindy_vdr.h



