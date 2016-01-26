FROM ubuntu:trusty
ADD https://launchpad.net/gcc-arm-embedded/5.0/5-2015-q4-major/+download/gcc-arm-none-eabi-5_2-2015q4-20151219-linux.tar.bz2 /gcc-arm-none-eabi-5_2-2015q4-20151219-linux.tar.bz2

RUN dpkg --add-architecture i386 && \
apt-get update && \
apt-get install -y libc6:i386 libncurses5:i386 libstdc++6:i386 && \
tar xvjf /gcc-arm-none-eabi-5_2-2015q4-20151219-linux.tar.bz2 && \
mv /gcc-arm-none-eabi-5_2-2015q4 /gcc && \
rm -rf /*.tar.bz2 && \
rm -rf /gcc/share/doc

ENTRYPOINT /bin/bash