.. role:: bash(code)
   :language: bash
Getting Started
===============

The Getting started will helps you to set-up your environment and to understand Foreman.

Foreman
--------

Foreman is a complete lifecycle management tool for physical and virtual servers. It gives system administrators the power to easily automate repetitive tasks, quickly deploy applications, and proactively manage servers, on-premise or in the cloud.

A Foreman installation will always contain a central foreman instance that is responsible for providing the Web based GUI, node configurations, initial host configuration files, etc. However, if the foreman installation supports unattended installations then other operations need to be performed to fully automate this process. The smart proxy manages remote services and is generally installed with all Foreman installations to manage TFTP, DHCP, DNS, Puppet, Puppet CA, Ansible, Salt, and Chef.

.. note:: For this documentation, we will only use TFTP, DHCP, DNS and Ansible.

Environment
------------------

For your tests, I recommand using :

* Virtual Machine (with Virtualbox as provider)
* Centos/7
* Ansible 2.3


Once you have those requirements, you can start learning about TFTP, DHCP, DNS and Ansible.

.. seealso:: Services
