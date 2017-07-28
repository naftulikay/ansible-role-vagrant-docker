# ansible-role-vagrant-docker [![Build Status][svg:travis]][travis]

An Ansible role for installing, configuring, and starting Docker within a Vagrant machine. Simply depends on the
upstream [`naftulikay.docker`][docker-galaxy] and [`naftulikay.vagrant-base`][vagrant-base-galaxy] roles and
specifies that `vagrant_user` should be added to the `docker` system group.

Available on Ansible Galaxy at [`naftulikay.vagrant-docker`][galaxy].

## Requirements

Officially tested operating systems are listed in the Galaxy manifest.

## Role Variables

<dl>
  <dt><code>vagrant_user</code></dt>
  <dd>The user name of the Vagrant user, defaults to <code>vagrant</code>.</dd>
<dl>

> Please see the upstream [`naftulikay.vagrant-base`][vagrant-base] and [`naftulikay.docker`][docker] roles for
additional supported variables.

## Dependencies

None.

## Example Playbook

Here are some example playbooks to get started with.

### Defaults

Simply get that Docker dockering in Vagrant:

```yaml
---
- name: install
  hosts: all
  become: true
  roles: [vagrant-docker]
```

If your Vagrant box uses a non-`vagrant` name for the Vagrant user:

```yaml
---
- name: install
  hosts: all
  become: true
  vars:
    vagrant_user: notvagrant
  roles: [vagrant-docker]
```

## License

MIT


 [svg:travis]: https://travis-ci.org/naftulikay/ansible-role-vagrant-docker.svg?branch=master
 [travis]: https://travis-ci.org/naftulikay/ansible-role-vagrant-docker
 [galaxy]: https://galaxy.ansible.com/naftulikay/vagrant-docker/
 [vagrant-base]: https://galaxy.ansible.com/naftulikay/vagrant-base/
 [docker]: https://galaxy.ansible.com/naftulikay/docker/
