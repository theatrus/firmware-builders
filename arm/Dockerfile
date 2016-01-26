FROM ubuntu:trusty
MAINTAINER Yann Ramin <yann@theatr.us>

ADD TARFILE /

RUN dpkg --add-architecture i386 && \
apt-get update && \
apt-get install -y libc6:i386 libncurses5:i386 libstdc++6:i386 && \
mv /gcc-arm-none-eabi-VERSION /gcc && \
rm -rf /gcc/share/doc && \
apt-get clean && \
rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENTRYPOINT /bin/bash