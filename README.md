Role Name
=========

This Role enables easy scalable deployment of the Bitflux Memory optimization system.

Requirements
------------

No additional dependencies

Role Variables
--------------

Default variables are as follows
bitflux_deviceIdTemplate: (Defaults to inventory_host_name)should be something that will be unique per machine. Using hostnames, or inventory values works well. Optionally adding a suffix may be helpful.
bitflux_key: (default is an invalid string, required)This is the token or key used to enable bitflux to run, found on cloud.bitflux.ai under credentials, noted as APIToken 
bitflux_enableKernel: (default false) setting this field to true, replaces the default kernel with a patched version of the same, enabling proactive memory management. kernel patch details can be found at https://github.com/resurgentech/bitflux_patch
This naming may change for clarification
They are named this way to avoid confusion, and allow overriding of individual variables.

Dependencies
------------

There are no other dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: bitflux, bitflux_enableKernel: true, bitflux_key: {{mykeyvar}}, bitflux_deviceIdTemplate: {{inventory_hostname_short}}-mysql }

License
-------

MIT
