# [redis](#redis)

Install and configure redis on your system.

|GitHub|GitLab|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![github](https://github.com/robertdebock/ansible-role-redis/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-redis/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-redis/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-redis)|[![quality](https://img.shields.io/ansible/quality/30211)](https://galaxy.ansible.com/robertdebock/redis)|[![downloads](https://img.shields.io/ansible/role/d/30211)](https://galaxy.ansible.com/robertdebock/redis)|[![Version](https://img.shields.io/github/release/robertdebock/ansible-role-redis.svg)](https://github.com/robertdebock/ansible-role-redis/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: robertdebock.redis
```

The machine needs to be prepared. In CI this is done using `molecule/default/prepare.yml`:

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.epel
    - role: robertdebock.apt_autostart
    - role: robertdebock.sysctl
      sysctl_items:
        - name: vm.overcommit_memory
          value: 1
    - role: robertdebock.grub
      grub_options:
        - option: transparent_hugepage
          value: never
```

Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.


## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/robertdebock/ansible-role-redis/blob/master/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[robertdebock.apt_autostart](https://galaxy.ansible.com/robertdebock/apt_autostart)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-apt_autostart/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-apt_autostart/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock/ansible-role-apt_autostart/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-apt_autostart)|
|[robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-bootstrap)|
|[robertdebock.epel](https://galaxy.ansible.com/robertdebock/epel)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-epel/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock/ansible-role-epel/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-epel)|
|[robertdebock.sysctl](https://galaxy.ansible.com/robertdebock/sysctl)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-sysctl/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-sysctl/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock/ansible-role-sysctl/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-sysctl)|
|[robertdebock.grub](https://galaxy.ansible.com/robertdebock/grub)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-grub/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-grub/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock/ansible-role-grub/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-grub)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/ansible-role-redis/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|alpine|all|
|el|8|
|debian|all|
|fedora|all|
|opensuse|all|
|ubuntu|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-redis/issues)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[robertdebock](https://robertdebock.nl/)

Please consider [sponsoring me](https://github.com/sponsors/robertdebock).
