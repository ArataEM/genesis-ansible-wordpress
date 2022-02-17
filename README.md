# Genesis DevOps School: Решение кейса
Установка Wordpress с помощью Ansible в Docker контейнерах

Устанавливаем на рабочей станции git и Ansible:

```shell
$ sudo apt update
$ sudo apt install git
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

Так-же необходимо установить коллекцию плагинов для Docker:

```shell
$ ansible-galaxy collection install community.docker
```

Клонируем и переходим в репозиторий:

```shell
$ git clone https://github.com/ArataEM/genesis-ansible-wordpress.git
$ cd genesis-ansible-wordpress
```

Для установки локально, согласно условиям кейса, выполняем команду:
```shell
$ ansible-playbook playbook_local.yaml -K
```
