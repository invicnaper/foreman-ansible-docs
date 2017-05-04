.. role:: bash(code)
   :language: bash
Installing Foreman
==================

Foreman is using a lot of components, and installing them manualy will take a lot of time, so we are using an Ansible playbook to install foreman.


Foreman-ansible-postgres Playbook
-------------------------

The foreman-ansible-postgres is a fork of foreman-ansible, that support PostgreSQL and Powerdns.

the playbook contains multiple different roles with numerous customizable variables, which provide the following features:

* Setup database (PostgreSQL)
* Setup webserver (plain nginx as a proxy or nginx-passenger)
* Setup isc-dhcp-server
* Setup TFTP server
* Setup powerdns
* Setup foreman-proxy
* Setup Foreman including configuration (templates, hosts, domains, etc.)

.. warning:: None of the roles will install Puppet or use the official foreman-installer, instead the plain Foreman packages are used!

.. note:: In addition this playbook makes use of foreman-yml to automatically configure Foreman through the API based on a YAML file, which includes adding all templates, OS, media, hosts, etc. and linking them accordingly.


Supported distributions:
~~~~~~~~~~~~~~~~~~~~~~~~

* Debian 7 & 8
* Ubuntu 14.04 & 16.04
* CentOS 6 & 7
* Red Hat Enterprise Linux 6 & 7

Github repo
~~~~~~~~~~~~~~

You clone the repo from: https://github.com/invicnaper/foreman-ansible-postgres
