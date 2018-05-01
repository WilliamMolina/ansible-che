FROM  wondercode/ubuntu-ssh:16.04
MAINTAINER William Molina "https://github.com/williammolina"
RUN apt-get update && apt-get install -y software-properties-common
RUN apt-add-repository -y ppa:ansible/ansible
RUN apt-get update && apt-get install -y ansible
COPY hosts /etc/ansible/hosts
