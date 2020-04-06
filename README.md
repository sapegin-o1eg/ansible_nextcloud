TESTWORK
=========

Description
------------
This repo contains Vagrantfile, ansible playbook (playbook,yml) and related roles for deploying virtual machine
Ubuntu 18.04 LTS 64 with Nextcloud + Nginx + php-fpm + Postgresql + Redis

Requirements
------------

On host machine must be installed
* [Vagrant](https://www.vagrantup.com/)
* [Ansible](https://www.ansible.com/)
* [Python](https://www.python.org/)
* [VirtualBox](https://www.virtualbox.org/)

How to use
----------------
In terminal:

    $ git clone https://github.com/sapegin-o1eg/ansible_nextcloud
    $ cd ansible_nextcloud
    $ vagrant up

After finishing, Nextcloud is available by URL [http://127.0.0.1:8087](http://127.0.0.1:8087) on the host machine.
To log in, use default username and password:
* user: root
* pass: fei8Ichieghie


Feel free to edit variables/parameters on your own.

To delete the virtual machine, enter command (you must be at the same level as the Vagrantfile):

    $ vagrant destroy
    
Or at any directory use the command:

    $ vagrant destroy $(vagrant global-status | awk '/ansible_owncloud/ {print $1}')

To log in to the virtual machine via ssh use command (you must be at the same level as the Vagrantfile):

    $ vagrant ssh
    
Or at any directory use the command:

    $ vagrant ssh $(vagrant global-status | awk '/ansible_owncloud/ {print $1}')

Disclaimer
----------------
The repo is not for production use.
Only for testing purposes on the local machine and to get familiar with the used stack of the technologies. 

License
-------

BSD

Author Information
------------------

Sapegin Oleg 