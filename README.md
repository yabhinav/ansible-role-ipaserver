IPA Server 
==========

[![Build Status](https://travis-ci.org/yabhinav/ansible-role-ipaserver.svg?branch=master)](https://travis-ci.org/yabhinav/ansible-role-ipaserver)

A role that installs and configures IPA server.

Requirements
------------
- Requires your Linux machine doesn't have other kerberos installations and configurations like MIT-KDC and ActiveDirectory, krb5.conf will be over written by IPA installation.
- If mod_ssl is configured to listen to port 443 it will be reconfigured to use port 10443 as a direct conflict with mod_nss installation.


Role Variables
--------------

Mandatory variable are listed here with default values :

	ipaserver_realm: "EXAMPLE.COM"
	ipaserver_domain: "example.com"

	ipaserver_admin_password : * * * * * * * * * * * 
	ipaserver_dir_admin_password : * * * * * * * * * * * 


Optional variables are listed here with default values :

	ipaserver_configure_ssh: True
	ipaserver_configure_sshd: True
	ipaserver_hbac_allow: True

	ipaserver_idstart: 5000
	ipaserver_idmax: False

	ipaserver_setup_ntp: True 

	ipaserver_setup_dns: False
	ipaserver_ssh_trust_dns: False
	ipaserver_dns_forwarder: 8.8.8.8

	ipaserver_ui_redirect: True

Other variables that should not be changed :

	ipaserver_admin_username: admin


Dependencies
------------

None.

Example Playbook
----------------

	- hosts: localhost
	  become_user: True
	  gather_facts: True
	  
	  roles:
	    - yabhinav.ipaserver

Issues
------

- It is not advised to execute this role from ansible running on python-virtualenv on Ubuntu16.04 locally due to this [issue](https://github.com/pypa/virtualenv/issues/1022) . Also have a look at same [issue here](https://github.com/ansible/ansible/issues/21691) 
- Freeipa-admintools is available only in Ubuntu16.04, So Debian 7,8 and Ubuntu 12.04 and 14.04 support not present for this role


License
-------

MIT


Author Information
------------------

Created by [Abhinav Yalamanchili](https://yabhinav.github.com)
