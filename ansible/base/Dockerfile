# BASE image - used as a starting point by MASTER and HOST images

# I use official Ubuntu 17.10 image as a starting point
FROM ubuntu:latest

# install required packages

# RUN echo -n "deb http://archive.ubuntu.com/ubuntu focal main universe multiverse restricted \n deb http://security.ubuntu.com/ubuntu/ focal-security main multiverse universe restricted \n deb http://archive.ubuntu.com/ubuntu focal-updates main multiverse universe restricted" > /etc/apt/sources.list

# RUN apt-mark unhold $(apt-mark showhold)

ENV TZ=Asia/Kolkata \
    DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get autoremove \
    && apt-get install --no-install-recommends --no-install-suggests -y \
        aptitude* iputils-ping net-tools man vim openssh-server python3 \
    && rm -rf /var/lib/apt/lists/*

# ensure that required directories are created
RUN mkdir /var/run/sshd
RUN mkdir /root/.ssh
