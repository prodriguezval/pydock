FROM python:3-onbuild
MAINTAINER Pablo Rodriguez <prodriguez.val@gmail.com>
USER root
RUN apt-get update && apt-get install -yq --no-install-recommends \
    git \
    vim \
    ssh \
    unzip \
    && apt-get clean && \
rm -rf /var/lib/apt/lists/*

#####################################
# Non-Root User:
#####################################
# Add a non-root user to prevent files being created with root permissions on host machine.
ARG PUID=1000
ARG PGID=1000
RUN groupadd -g $PGID pydock && \
    useradd -u $PUID -g pydock -m pydock

#####################################
# PIP:
#####################################
USER pydock
# Add the requirements.txt
COPY ./requirements.txt /home/pydock/
RUN mkdir /home/pydock/dev
USER root
RUN chown -R pydock:pydock /home/pydock/
USER pydock
# Set default work directory
WORKDIR /home/pydock/dev
