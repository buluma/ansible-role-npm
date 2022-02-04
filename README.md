# [npm](#npm)

Install npm on your system.

|GitHub|GitLab|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-npm/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-npm/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-npm/badges/main/pipeline.svg)](https://gitlab.com/buluma/ansible-role-npm)|[![quality](https://img.shields.io/ansible/quality/57926)](https://galaxy.ansible.com/buluma/npm)|[![downloads](https://img.shields.io/ansible/role/d/57926)](https://galaxy.ansible.com/buluma/npm)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-npm.svg)](https://github.com/buluma/ansible-role-npm/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.npm
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
    - role: robertdebock.ca_certificates
    - role: robertdebock.epel
```


## [Role Variables](#role-variables)

The default values for the variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for npm

# The npm_registry is mapped in `vars/main.yml` to a usable default,
# you can overwrite it here if required.
npm_registry: "{{ _npm_registry[ansible_distribution] | default(_npm_registry['default'] ) }}"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-npm/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[robertdebock.bootstrap](https://galaxy.ansible.com/buluma/robertdebock.bootstrap)|[![Build Status GitHub](https://github.com/buluma/robertdebock.bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/robertdebock.bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/robertdebock.bootstrap/badges/main/pipeline.svg)](https://gitlab.com/buluma/robertdebock.bootstrap)|
|[robertdebock.ca_certificates](https://galaxy.ansible.com/buluma/robertdebock.ca_certificates)|[![Build Status GitHub](https://github.com/buluma/robertdebock.ca_certificates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/robertdebock.ca_certificates/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/robertdebock.ca_certificates/badges/main/pipeline.svg)](https://gitlab.com/buluma/robertdebock.ca_certificates)|
|[robertdebock.epel](https://galaxy.ansible.com/buluma/robertdebock.epel)|[![Build Status GitHub](https://github.com/buluma/robertdebock.epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/robertdebock.epel/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/robertdebock.epel/badges/main/pipeline.svg)](https://gitlab.com/buluma/robertdebock.epel)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.co.ke/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-npm/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|alpine|all|
|amazon|Candidate|
|el|8|
|debian|bullseye|
|fedora|all|
|ubuntu|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some roles can't run on a specific distribution or version. Here are some exceptions.

| variation                 | reason                 |
|---------------------------|------------------------|
| debian:testing | The repository 'https://deb.nodesource.com/node_10.x bullseye Release' does not have a Release file. |


If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-npm/issues)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)
