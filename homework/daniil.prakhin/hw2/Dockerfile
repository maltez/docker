# This is Dockerfile for 2nd homework:
# - Create a new image, based on Ubuntu official,
#   which will have Docker inside it.
#   Test => docker -v => Passed

# Initial image:
FROM ubuntu:18.04

# Basic information about new image:
LABEL version="1.0.1"
LABEL maintainer="Daniil.Prakhin"

# Initial commands we need to use.
# To have Docker installed inside image we need to:
# - add official Docker repository inside it
# - install additional OS packages
# - install Docker packages
# Right after image run we have root permissions
# so, we don't need to use sudo here

# Install additional OS packages
RUN apt-get update \
&& apt-get install -yq --no-install-recommends dialog liberror-perl libterm-readline-gnu-perl \
&& apt-get install -yq --no-install-recommends ca-certificates openssl libssl1.1 \
&& apt-get install -yq --no-install-recommends apt-transport-https \
&& apt-get install -yq --no-install-recommends curl libcurl4 gnupg-agent software-properties-common

# Add repository and it's gpg key into system
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
RUN add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# Install additional OS packages
RUN apt-get install -yq --no-install-recommends git git-man pigz \
&& apt-get install -yq --no-install-recommends aufs-tools cgroupfs-mount

# Install Docker packages & remove packages cache
RUN apt-get install -yq --no-install-recommends docker-ce docker-ce-cli containerd.io \
&& apt-get autoclean

ENTRYPOINT ["/usr/bin/docker","-v"]

###
