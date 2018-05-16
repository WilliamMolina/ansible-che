FROM centos:7
RUN yum -y install openssh-server
RUN mkdir /var/run/sshd
#Set root password
RUN echo 'root:random' |chpasswd
#Allow login as root
RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config
RUN ssh-keygen -t rsa -N '' -f /etc/ssh/ssh_host_rsa_key
RUN ssh-keygen -t ecdsa -N '' -f /etc/ssh/ssh_host_ecdsa_key
RUN ssh-keygen -t ed25519 -N '' -f /etc/ssh/ssh_host_ed25519_key
EXPOSE 22
#Start ssh
CMD ["/usr/sbin/sshd", "-D"]
