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
Roles managing mysql, apache and certificates.

This role will drop its own apache configuration in `/etc/httpd/conf.d/linotp.conf`.

Example Playbook
----------------
Example:
```
- hosts: servers
  roles:
    - linotp
```

TODO
----
- Handle the apache configuration with the apache role.

Licence
-------
Licensed under [CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

Author Information
------------------
Luis Gracia <luis.gracia@ebi.ac.uk>
