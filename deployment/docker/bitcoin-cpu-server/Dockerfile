FROM ubuntu:20.04

USER root

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
    tini \
    wget \
    ca-certificates \
    sudo \
    locales \
    fonts-liberation \
    run-one && \
    apt-get clean && rm -rf /var/lib/apt/lists/* && \
    echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen

RUN DEBIAN_FONTEND="noninteractive" apt-get update -y
RUN DEBIAN_FONTEND="noninteractive" apt-get upgrade -y
RUN DEBIAN_FONTEND="noninteractive" apt-get install \
    apt-utils \
    build-essential \
    curl \
    dnsutils \
    dos2unix \
    gcc \
    git \
    gnupg2 \
    htop \
    iputils-ping \
    less \
    net-tools \
    rsync \
    s3fs \
    tree \
    vim \
    -y

RUN apt install -y build-essential libtool autotools-dev automake pkg-config bsdmainutils curl git
RUN apt install -y python3
RUN apt install -y libevent-dev libboost-dev libboost-test-dev
RUN apt install -y libsqlite3-dev
RUN apt install -y libminiupnpc-dev libnatpmp-dev
RUN apt install -y libzmq3-dev
RUN apt install -y systemtap-sdt-dev
RUN apt install -y libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools
RUN apt install -y nsis
RUN apt install -y libqrencode-dev

WORKDIR /srv

RUN git clone https://github.com/bitcoin/bitcoin.git

WORKDIR /srv/bitcoin

RUN ls .

RUN ./autogen.sh

RUN ./configure \
  --enable-lto \
  --enable-util-cli \
  --enable-util-tx \
  --enable-util-wallet \
  --enable-util-util \
  --disable-largefile \
  --with-gui=no \
  --with-qrencode

RUN make

