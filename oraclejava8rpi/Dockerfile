FROM debian:9-slim
ARG package=oracle-java8-jdk
COPY trusted-keys /trusted
RUN apt update && apt install -y gnupg2 && rm -rf /var/lib/apt/lists/*
RUN apt-key add /trusted 
RUN echo "deb http://raspbian.raspberrypi.org/raspbian/ stretch main contrib non-free rpi" >> /etc/apt/sources.list
RUN echo "deb http://archive.raspberrypi.org/debian/ stretch main ui" >> /etc/apt/sources.list
RUN mkdir -p /usr/share/man/man1/
RUN apt update && apt install -y ${package} && rm -rf /var/lib/apt/lists/*
