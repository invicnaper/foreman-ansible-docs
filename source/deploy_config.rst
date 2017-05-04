.. role:: bash(code)
   :language: bash
Deployment Configurations
=========================

This part will help you configuring ansible and services.

.. note:: Those configurations must be done on your local machine

Inventory file
---------------

First, you have to create an inventory file, on your local machine:

:bash:`$ nano /home/<user>/inventory`

and add
::

        <manage_ip>      ansible_user=<user>     ansible_become=true

Configure SSH Keys
-------------------

Generate SSH key
~~~~~~~~~~~~~~~~~

Create SSH key using:

:bash:`$ ssh-keygen -t rsa -b 4096`


Copy SSH key
~~~~~~~~~~~~~

Copy the ssh key using:

:bash:`$ ssh-copy-id <user>@<manage_ip>`
