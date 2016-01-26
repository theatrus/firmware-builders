.PHONY: all
all: download build

.PHONY: download
download: gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2 gcc-arm-none-eabi-5_2-2015q4-20151219-linux.tar.bz2

gcc-arm-none-eabi-5_2-2015q4-20151219-linux.tar.bz2:
	wget "https://launchpad.net/gcc-arm-embedded/5.0/5-2015-q4-major/+download/gcc-arm-none-eabi-5_2-2015q4-20151219-linux.tar.bz2"
	touch $@

gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2:
	wget "https://launchpad.net/gcc-arm-embedded/4.9/4.9-2015-q3-update/+download/gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2"
	touch $@

.PHONY: build

build:
	cat Dockerfile | perl -p -e 's/TARFILE/gcc-arm-none-eabi-5_2-2015q4-20151219-linux.tar.bz2/g or s/VERSION/5_2-2015q4/g' > Dockerfile.5_2-2015q4
	docker build -t theatrus/firmware-builder-arm:5_2-2015q4 -f Dockerfile.5_2-2015q4 .
	cat Dockerfile | perl -p -e 's/TARFILE/gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2/g or s/VERSION/4_9-2015q3/g' > Dockerfile.4_9-2015q3
	docker build -t theatrus/firmware-builder-arm:4_9-2015q3 -f Dockerfile.4_9-2015q3 .