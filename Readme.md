This container is provisioned with ansible installed.

Build args:

- ANSIBLE_VERSION (argument to specify Ansible version to install)

It also contains systemd faker (replacing systemd binaries) to make Ansible roles working on build stage (in dockerfiles) even when the roles are trying to restart services using initctl, service or systemctl.

What it does:

- Install Ansible
- Replace initctl by a script that calls /usr/sbin/service instead
- Replace systemctl by a script that just exit with code 0 (success)
- Rename original service command to service_real and copy a script as /usr/sbin/service, that execute service_real command in a trap (To ignore any errors. Useful for some services that check existence of others containers (backends for Varnish, for example), which are not available at build time).

Available tags:

- ubuntu-xenial