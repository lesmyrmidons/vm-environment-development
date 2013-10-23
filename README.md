vm-environment-development
==========================

Automating the installation of VM and mandatory packages for a Web application.

Requirements
------------

* Vagrant >=1.3.5
* Ansible >=1.3.3

Configuration
-------------

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

