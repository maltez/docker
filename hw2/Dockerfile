# it was based on article https://docs.docker.com/install/linux/docker-ce/ubuntu/
FROM ubuntu:18.04
MAINTEINER vbakin12@gmail.com

RUN apt-get update && apt-get install -qqy \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
    
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg |  apt-key add -
RUN add-apt-repository  "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" 

RUN  apt-get update
RUN  apt-get install -qqy docker-ce docker-ce-cli containerd.io 


CMD [ "docker", "-v"]
