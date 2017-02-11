IPA Server 
==========

[![Build Status](https://travis-ci.org/yabhinav/ansible-role-ipaserver.svg?branch=master)](https://travis-ci.org/yabhinav/ansible-role-ipaserver)

A role that installs and configures IPA server.

Requirements
------------
- Requires your Linux machine doesn't have other kerberos installation like MIT-KDC and AD configuration. krb5.conf will be over written by IPA installation.
- If mod_ssl is configure to listen to port 443 it will be reconfigured to use port 10443 as a direct conflict with mod_nss installation.


Role Variables
--------------

Mandatory variable are listed here with default values :

	ipaserver_realm: "TESTLAB"
	ipaserver_domain: "TESTLAB.EXAMPLE.COM"

	ipaserver_admin_password : * * * * * * * * * * * 
	ipaserver_dir_admin_password : * * * * * * * * * * * 


Optional variables are listed here with default values:

	ipaserver_configure_ssh: True
	ipaserver_configure_sshd: True
	ipaserver_dns_forwarder: 8.8.8.8
	ipaserver_hbac_allow: True
	ipaserver_idstart: 5000
	ipaserver_idmax: False
	ipaserver_setup_dns: True
	ipaserver_setup_ntp: True
	ipaserver_ssh_trust_dns: True
	ipaserver_ui_redirect: True
	ipaserver_manage_firewalld: True

Other variables that should not be changed :

	ipaserver_admin_username: admin


Dependencies
------------

None.

Example Playbook
----------------

	- hosts: localhost
	  remote_user: root
	  roles:
	    - yabhinav.ipaserver

License
-------

MIT


Author Information
------------------

Created by [Abhinav Yalamanchili](https://yabhinav.github.com)
