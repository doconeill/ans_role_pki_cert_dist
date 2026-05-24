# ans_role_pki_cert_dist
Distribute PKI/SSL certs from a central location

This role expects to get a cert, chain, cert+chain (fullchain) and key file from a source server (such as
a server running certbot), and then distribute it to the hosts calling the role.

By default, the files are stored in /etc/myssl and simply called "myssl_*". See the default variables for overriding them.
Variables for the source host and files are shown in defaults but not defined - they are intended to be set in a project.

It expects a group (defined as pki_certs_dist_group, by default "certs") for the certs to be set to so that non-root
services can make use of them. That group should already exist before the role is called.
