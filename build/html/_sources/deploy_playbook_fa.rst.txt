.. role:: bash(code)
   :language: bash
Deploy Foreman-ansible-postgres playbook
=========================================

This part will help you deploying the playbook **foreman-ansible-postgres** using **ansible-playbook**

Ansible-playbook
-----------------

To deploy the playbook on your manage node, use:

:bash:`$ ansible-playbook foreman.yml -i /home/<user>/inventory –ask-become-pass`

.. image:: http://i.imgur.com/l98iQAS.png

To test foreman, visit the url:

http://manage_ip/
