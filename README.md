# [Ansible role auto_update](#auto_update)

Install and configure automatic package updates on your system.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/robertdebock/ansible-role-auto_update/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-auto_update/actions)|[![gitlab](https://gitlab.com/robertdebock-iac/ansible-role-auto_update/badges/master/pipeline.svg)](https://gitlab.com/robertdebock-iac/ansible-role-auto_update)|[![downloads](https://img.shields.io/ansible/role/d/robertdebock/auto_update)](https://galaxy.ansible.com/robertdebock/auto_update)|[![Version](https://img.shields.io/github/release/robertdebock/ansible-role-auto_update.svg)](https://github.com/robertdebock/ansible-role-auto_update/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/robertdebock/ansible-role-auto_update/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: ansible-role-auto_update
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/robertdebock/ansible-role-auto_update/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: robertdebock.bootstrap
```

Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/robertdebock/ansible-role-auto_update/blob/master/defaults/main.yml):

```yaml
---
# defaults file for auto_update

# (RedHat like systems only) What type of updates to apply, valid choices are:
# default, security, security-severity:Critial, minimal, minimal-security, minimal-security-severity:Critical
auto_update_update_cmd: default

# (RedHat like systems only) Whether a message should be emitted when updates are available, were downloaded, or applied.
auto_update_message: false

# Whether updates should be downloaded when they are available.
auto_update_download_updates: true

# Whether updates should be applied when they are available.  Note
# that download_updates must also be yes for the update to be applied.
auto_update_apply_updates: false

# Maximum amout of time to randomly sleep, in minutes.
auto_update_random_sleep: 360
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/robertdebock/ansible-role-auto_update/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock-iac/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/robertdebock-iac/ansible-role-bootstrap)|
|[robertdebock.cron](https://galaxy.ansible.com/robertdebock/cron)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-cron/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-cron/actions)|[![Build Status GitLab](https://gitlab.com/robertdebock-iac/ansible-role-cron/badges/master/pipeline.svg)](https://gitlab.com/robertdebock-iac/ansible-role-cron)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/ansible-role-auto_update/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/robertdebock/enterpriselinux)|9|
|[Debian](https://hub.docker.com/r/robertdebock/debian)|all|
|[Fedora](https://hub.docker.com/r/robertdebock/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/robertdebock/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-auto_update/issues).

## [License](#license)

[Apache-2.0](https://github.com/robertdebock/ansible-role-auto_update/blob/master/LICENSE).

## [Author Information](#author-information)

[robertdebock](https://robertdebock.nl/)

Please consider [sponsoring me](https://github.com/sponsors/robertdebock).
