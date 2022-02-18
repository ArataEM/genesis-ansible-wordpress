# Genesis DevOps School: Test task solution
Wordpress deploy with Ansible and Docker

## Prerequisites
### OS
Ubuntu >= 18.04

### git and Ansible

Installing software:

```shell
$ sudo apt update
$ sudo apt install git
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

Also this playbook requires Ansible community collection for Docker:

```shell
$ ansible-galaxy collection install community.docker
```

## Deploy
Obtaining playbook and its dependencies from repository:

```shell
$ git clone https://github.com/ArataEM/genesis-ansible-wordpress.git
$ cd genesis-ansible-wordpress
```

To install locally you can use the following command:
```shell
$ ansible-playbook playbook_local.yaml -K
```

To install remotely using SSH you can edit `hosts` file:
```
[nodes]
<remote_host>   ansible_connection=SSH    ansible_user=<remote_user>
```
Where:
* remote_host - ip adress of remote host
* remote_user - user with configured SSH connection via SSH keys and sudo privileges

After configuration you can deploy Wordpress to remote host with command:

```shell
$ ansible-playbook playbook_local.yaml -K
```

