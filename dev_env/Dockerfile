FROM ubuntu:16.10

# Unicode support: (Solution to python3 not able to print unicode strings to
# console).
# https://github.com/docker/docker/issues/3696
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8

# Make sure we use bash and not sh:
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Install packages and some useful utils:
RUN apt update && \
    apt install -y \
	autoconf \
	build-essential \
	cmake \
	dirmngr \
	freeglut3-dev \
	g++ \
	gperf \
	libbz2-dev \
	libdbus-1-dev \
	libegl1-mesa-dev \
	libfreetype6-dev \
	libgles2-mesa-dev \
	libglib2.0-dev \
	libglu1-mesa-dev \
	libosmesa6-dev \
	libssl-dev \
	libxmu6 \
	libxmu-dev \
	sudo \
	xorg-dev && \
    apt install -y \
	curl \
	git \
	tmux \
	python \
	python-pip \
    	vim && \
    apt clean


# virtualenv:
RUN pip install virtualenvwrapper

# Create developer user:
RUN useradd -ms /bin/bash developer && \
    adduser developer sudo && \
    passwd -d developer

# echo "developer ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/developer

ENV HOME /home/developer
USER developer
