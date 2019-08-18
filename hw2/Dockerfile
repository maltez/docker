FROM 	ubuntu:latest

LABEL	version="1.0.0"
LABEL	maintainer="Volodymyr Kaliuzhnyi"

#Update the apt package index:
RUN		apt-get update

#Install packages to allow apt to use a repository
RUN		apt-get install\
    	apt-transport-https \
    	ca-certificates \
    	curl \
    	gnupg-agent \
    	software-properties-common -y

#Add Docker’s official GPG key:
RUN		curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -

#Set up the stable repository:
RUN		add-apt-repository \
   		"deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   		$(lsb_release -cs) \
   		stable"

#Update the apt package index:
RUN		apt-get update

#Install the latest version of Docker Engine - Community and containerd:
RUN		apt-get install docker-ce docker-ce-cli containerd.io -y

CMD 	[ "docker", "-v"]
