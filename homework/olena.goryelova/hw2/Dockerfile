FROM ubuntu:18.04

LABEL version="1.0.1"
LABEL maintainer="Olena Goryelova"

RUN apt-get update \
&& apt-get install -yq --no-install-recommends dialog liberror-perl libterm-readline-gnu-perl \
&& apt-get install -yq --no-install-recommends ca-certificates openssl libssl1.1 \
&& apt-get install -yq --no-install-recommends apt-transport-https \
&& apt-get install -yq --no-install-recommends curl libcurl4 gnupg-agent software-properties-common

RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
RUN add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

RUN apt-get install -yq --no-install-recommends git git-man pigz \
&& apt-get install -yq --no-install-recommends aufs-tools cgroupfs-mount

RUN apt-get install -yq --no-install-recommends docker-ce docker-ce-cli containerd.io \
&& apt-get autoclean

ENTRYPOINT ["/usr/bin/docker","-v"]
