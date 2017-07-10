LinOTP
======
Install and configure LinOTP.

The current apache configuration dropped by this role uses ldap authentication to restrict access to certain urls. `linotp_ldap_url` and `linotp_ldap_filter` control this behaviour.

Encryption keys are blank by default and should be configured with `linotp_encryption_key`, `linotp_audit_private_key` and `linotp_audit_public_key`.

Requirements
------------
See `meta/main.yml`.

Role Variables
--------------
See `defaults/main.yml`.

Dependencies
------------
This roles depends on apache and certificates being present in the same server. Additionally a mysql database should be accessible by LinOTP (see variables prefixed with `linotp_db_`). Se an example of susccesful roles used to manage dependencies below.

This role will drop its own apache configuration in `/etc/httpd/conf.d/linotp.conf`.

Example Playbook
----------------
Example:
```
- hosts: servers
  roles:
    - mysql
    - jdauphant.ssl-certs
    - geerlingguy.apache
    - linotp
```

TODO
----
- Handle the apache configuration with the apache role.

Licence
-------
Released under the [MIT license](https://opensource.org/licenses/MIT).

Author Information
------------------
Luis Gracia while at [EMBL-EBI](http://www.ebi.ac.uk/):
- luis.gracia [at] ebi.ac.uk
- GitHub at [luisico](https://github.com/luisico)
- Galaxy at [luisico](https://galaxy.ansible.com/luisico)
