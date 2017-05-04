.. role:: bash(code)
   :language: bash
Services
===============

Foreman needs many services for doing his job, this section will introduce you those different services

TFTP
-----
Trivial File Transfer Protocol (TFTP) is a simple lockstep File Transfer Protocol which allows a client to get a file from or put a file onto a remote host. One of its primary uses is in the early stages of nodes booting from a local area network. TFTP has been used for this application because it is very simple to implement.

.. note:: Tftp is used along with Pxelinux, for booting from PXE.

DHCP
-----
The Dynamic Host Configuration Protocol (DHCP) is a standardized network protocol used on Internet Protocol (IP) networks. The DHCP is controlled by a DHCP server that dynamically distributes network configuration parameters.

.. note:: The server where Foreman is installed is playing the DHCP server.

Ansible
--------
Ansible is used for installing Foreman, and then used as a plugin in Foreman for ghatering facts

.. note:: Playbooks were tested with Ansible 2.3

Overview
----------
To understand the use of every service, we've got two machines:

* The Manage node (where foreman is installed)
* The Controller node (the host we want to build)


.. tip:: When the controller node is booting on PXE mode, the Manage node who's the DHCP server, will assign to the controller node an Ip address, along with a fileName. The filename is the **pxelinux.0** (**/var/lib/tftpboot/pxelinux.0**), after that, the controller node try to connect to the TFTP server to download the **pxelinux.0** and the **pxelinux.cfg** and then loading linux image. When the Controller is built, we can deploy playbooks using Ansible.
