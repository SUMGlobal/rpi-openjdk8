FROM resin/armv7hf-debian-qemu:latest
MAINTAINER Charles Walker <cwalker@sumglobal.com>
RUN [ "cross-build-start" ]


# deal with slim variants not having man page directories (which causes "update-alternatives" to fail)
RUN set -ex; \
	if [ ! -d /usr/share/man/man1 ]; then \
		mkdir -p /usr/share/man/man1; \
	fi;
#
# Pull Zulu OpenJDK binaries from official repository:
#
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 0x219BD9C9
RUN echo "deb http://repos.azulsystems.com/debian stable  main" >> /etc/apt/sources.list.d/zulu.list
RUN apt-get -qq update
RUN apt-get -y install zulu-embedded-8

RUN update-alternatives --config java

RUN [ "cross-build-end" ]  
