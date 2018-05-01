#Ansible quick start using Docker and Eclipse Che#
- apt-get install software-properties-common
- apt-add-repository ppa:ansible/ansible
- apt-get update
- apt-get install ansible

# Generate ssh key
- ssh-key gen -t rsa

# Copy ssh key to hosts
- ssh-copy-id hostname

# install ping in all hosts
- ansible all -m apt -a "name=iputils-ping state=present"

# playbook
- ansible-playbook example.yml
