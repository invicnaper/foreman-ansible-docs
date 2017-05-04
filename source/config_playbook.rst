.. role:: bash(code)
   :language: bash
OS Configurations
==============

To avoid errors while deploying the playbook, you have to do some pre-deploy configuration

.. note:: Those configurations must be done on the manage node

FQDN configuration
---------------------
Open :file:`/etc/hostname`:

:bash:`# nano /etc/hostname`

and add
::

        <hostname>

Open :file:`/etc/hosts`:

:bash:`# nano /etc/hosts`

and add
::

        127.0.0.1       localhost
        #127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
        ::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
        <ip>  <domain> <hostname>

Disable SElinux
----------------
To disable SElinux, open :file:`/etc/sysconfig/selinux`:

:bash:`# nano /etc/sysconfig/selinux`

write
::

      SELINUX=disabled

Open required ports
--------------------
The required ports are:

* 67
* 69
* 80
* 443

to open them, use:

:bash:`# firewall-cmd --permanent -–add-port=67/udp`

:bash:`# firewall-cmd --permanent -–add-port=69/udp`

:bash:`# firewall-cmd --permanent -–add-port=80/udp`

:bash:`# firewall-cmd --permanent -–add-port=443/udp`

.. seealso:: Install Playbook requirements
