Oracle Instant Client Role
=========
The `ansible-oracle-instant-client-role` role installs the basiclite version of the Oracle
database client library for a Linux-based machine.  The role installs via the .zip file method, as opposed to using RPMs.  This allows for a bit more consistency between Ubuntu and RedHat distros, as the former would require installing the `alien` package to convert the rpms to deb files.  Currently, the role ships with the necessary .zip files to install a particular version of the basiclite client, along with sqlplus and the SDK binaries needed to build from source.

In addition, a sqlnet.ora file is created to allow for client-side encryption of database requests, and client side logging.  See https://docs.oracle.com/database/121/NETRF/sqlnet.htm#NETRF006 for details on parameters to that file referenced in the Role Variables section below.

Requirements
------------

None

Role Variables
--------------

oracle_client_adr_tracing_enabled -> maps to DIAG_ADR_ENABLED
    NOTE: default value is off, while Oracle default is on
oracle_client_log_dir -> maps to TRACE_DIRECTORY_CLIENT in sqlnet.ora file
oracle_client_log_level -> maps to TRACE_LEVEL_CLIENT in sqlnet.ora file
oracle_client_encryption_level -> maps to both ENCRYPTION_CLIENT and CRYPTO_CHECKSUM_CLIENT

Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
