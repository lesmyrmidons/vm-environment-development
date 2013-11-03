Installation Ansible
====================

Requirements
------------

* python-jinja2
* python-yaml
* python-paramiko

For Debian and derivate:
```bash
$ sudo aptitude install -y python-jinja2 python-yaml python-paramiko
```

Ansible
-------

Download ansible from github:
[https://github.com/ansible/ansible.git](https://github.com/ansible/ansible.git)
```bash
$ git clone https://github.com/ansible/ansible.git
```

Stand you in version 1.3.3:
```bash
$ git checkout tags/v1.3.3
```

Execute the following command:
```bash
$ make
$ sudo make install
```

Checking the installed release:
```bash
$ ansible --version
```
