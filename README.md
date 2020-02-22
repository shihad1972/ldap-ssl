LDAP SSL
=========

Configure SSL communications for the openldap software

Requirements
------------

Openldap should be installed and running for this role.
You should also have an SSL key pair (1 private key, 1 public certificate).
You can place these into the files/ directory in the same directory as your playbooks.
You can name them with the ldap_cert_file and ldap_key_file variables, or you can use the
 defaults of {{ ldap_host_name }}.pem and {{ ldap_host_name }}.crt

Role Variables
--------------

  - ldap_host_name: Set to the CN of the SSL certificate; defaults to ansible_fqdn.
  - cert_file: Filename of the SSL certificate. Defaults to ldap_host_name.pem
  - key_file: Filename of the SSL private key. Defaults to ldap_host_name.crt

Dependencies
------------

No direct dependencies, but this role does expect a working openldap installation.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ldap_ssl,
             cert_file: my.host.com.crt,
             key_file: my.host.com.key }

License
-------

GPLv3

Author Information
------------------

Iain M Conochie <iain@thargoid.co.uk>
