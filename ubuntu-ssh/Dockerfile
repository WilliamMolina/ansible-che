FROM       ubuntu:16.04
MAINTAINER William Molina "https://github.com/williammolina"
#Install ssh
RUN apt-get update && apt-get install -y openssh-server
RUN mkdir /var/run/sshd
#Set root password
RUN echo 'root:random' |chpasswd
#Allow login as root
RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config
EXPOSE 22
#Start ssh
CMD ["/usr/sbin/sshd", "-D"]
