.. role:: bash(code)
   :language: bash
Playbook Configuration
======================

This part will help you configure services installed by the playbook


DHCP
-----

To configure the DHCP server, open :file:`vars/examples.yml`

and edit the part:
::

      isc_dhcp_server_subnet:
        - netaddress: 192.168.121.0
          netmask: 255.255.255.0
          gateway: 192.168.121.1
          domain: lab.local
          domain_search: lab.local
          dns: 192.168.121.1
          range: 192.168.121.20 192.168.121.100


TFTP
-----

To configure the TFTP server, open :file:`roles/tftp/default/main.yml`

and edit the part:
::

      tftp_dir: /srv/tftp

      tftp_pxe_dir:
      - boot
      - pxelinux.cfg

      tftp_hpa_address: "0.0.0.0:69"
      tftp_hpa_options: --secure

      tftp_xinetd_socket_type: dgram
      tftp_xinetd_protocol: udp
      tftp_xinetd_wait: "yes"
      tftp_xinetd_service_user: root
      tftp_xinetd_server: /usr/sbin/in.tftpd
      tftp_xinetd_server_args: "--user {{ tftp_user }} --secure {{ tftp_dir }}"
      tftp_xinetd_disable: "no"
       

PostgreSQL
-----------

.. todo:: Edit PostgreSQL conf

PowerDNS
---------

.. warning:: .. deprecated:: 1.0
                moved to *powerdns-playbook*.


Foreman-proxy
-------------

To configure Foreman proxy, open :file:`roles/foreman-proxy/default/main.yml`:

and edit the part:
::

      foreman_proxy_port: 8000
      foreman_proxy_protocol: http
      foreman_proxy_bind_host: "{{ ansible_default_ipv4.address }}"

      foreman_proxy_foreman_url: "http://127.0.0.1"

      foreman_proxy_dhcp: true
      foreman_proxy_dhcp_protocol: http
      foreman_proxy_dhcp_server: 127.0.0.1
      foreman_proxy_dhcp_subnets: "[]"
      foreman_proxy_dhcp_omapi_port: 7911

      foreman_proxy_tftp: true
      foreman_proxy_tftp_protocol: http
      foreman_proxy_tftp_dir: /srv/tftp
      foreman_proxy_tftp_pxe_dir:
      - boot
      - pxelinux.cfg


Foreman-yml
------------

To configure foreman-yml, open :file:`roles/foreman-yml/default/main.yml`

and edit the part:
::

      foreman_yml_api_url: "http://localhost:80"
      foreman_yml_api_username: admin
      foreman_yml_api_password: foreman 


Foreman
-------

To configure foreman-yml, open :file:`roles/foreman/default/main.yml`
