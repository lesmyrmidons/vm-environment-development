vm-environment-development
==========================

Automating the installation of VM and mandatory packages for a Web application.

Requirements
------------

* [Vagrant >=1.5](docs/vagrant-install.md)
* [Ansible >=1.6.1](docs/ansible-install.md)
* lsyncd

Configuration
-------------

Install role dependency:

```bash
$ ansible-galaxy install leonidas.nvm
$ ansible-galaxy install geerlingguy.apache
```

Download and move to folder:

```bash
$ cd /path/vm-environment-development
```
Copy the file `parameters.rb.dist` to `parameters.rb`:

```bash
$ cp parameters.rb.dist parameters.rb
```
Change the file `parameters.rb` as desired.

Run
---

To run VM and execute ansible for install all package:

```bash
$ vagrant up --provision
```

Synchronize the project with the VM to develop
----------------------------------------------

To do this, we will use lsyncd. Have to run it once.

```bash
$ lsyncd -rsyncssh /folder/project vagrant@192.168.40.10 /vagrant/project/
```

Installed application
---------------------

* Ajenti (Web administration server)
* Mariadb (equal mysql)
* MongoDB (No-SQL v2.6.1)
* PHP5 (PHP 5.4.x)
* Composer (Dependency manager for PHP)
* Phpmyadmin (To administration database)
* nvm (Virtual Nodejs)
* git

License
-------

MIT / BSD
