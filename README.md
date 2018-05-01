# Ansible quick start using Docker and Eclipse Che
![Machines](screenshots/machines.png)
# 1. Setup workspace
- Open Eclipse Che.
- Select "Stacks" and click "Build Stack From Recipe".
- In Compose Tab paste the content of [docker-compose.yml](https://github.com/WilliamMolina/ansible-che/blob/master/docker-compose.yml) file and click "OK".
- Set name and description for the new stack.
- Enable Exec, Terminal and Workspace API to "ansible" machine.
- For S's machines enable just Terminal.
- Click "Save".

Now you have a new Stack with four machines: one with ansible and three "servers".
Let's create a new workspace with that stack and start playing wth ansible.

## Generate ssh key
From ansible machine run the following command:
 `ssh-key gen -t rsa`

## Copy ssh key to hosts
Again, from ansible machine run `ssh-copy-id hostname` for every server (s1, s2 and s3).

# 2. Play with Ansible

## Install ping in all hosts
 `ansible all -m apt -a "name=iputils-ping state=present"`

## Do the same with a  playbook
`ansible-playbook example.yml`
