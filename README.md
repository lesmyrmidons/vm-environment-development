vm-environment-development
==========================

Automating the installation of VM and mandatory packages for a Web application.

Requirements
------------

* [Vagrant >=1.5](docs/vagrant-install.md)
* [Ansible >=1.666666.1](docs/ansible-install.md)

Configuration
-------------

Install role dependency:

```bash
$ ansible-galaxy install leonidas.nvm
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

For run VM and execute ansible for install all package:

```bash
$ vagrant up --provision
```

Installed application
---------------------

* Ajenti (Web administration server)
* Mariadb (equal mysql)
* MongoDB (No-SQL)
* PHP5 (PHP 5.4.x)
* Phpmyadmin (To administration database)
* git

License
-------

MIT / BSD
