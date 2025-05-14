ansible-role-ansible-role-opentofu
=============

Ansible role to install the latest version of Opentofu

Requirements
------------

This role requires:
- Ansible 2.10 or higher
- Python 3.x
- Unzip package (for extracting the OpenTofu binary)
- Internet access to download OpenTofu from GitHub releases

Role Variables
--------------

The following variables are available:

| Variable | Description | Default |
|----------|-------------|---------|
| `opentofu_version` | Version of OpenTofu to install. Use 'latest' for the most recent version or specify a version like 'v1.6.0' | `latest` |
| `opentofu_path` | Directory where OpenTofu binary will be installed | `/usr/local/bin` (Linux) |

Dependencies
------------

This role has no dependencies on other roles.

Example Playbook
----------------

Basic usage:

```yaml
- hosts: servers
  roles:
    - role: diodonfrost.ansible-role-opentofu
```

With custom version:

```yaml
- hosts: servers
  roles:
    - role: diodonfrost.ansible-role-opentofu
      vars:
        opentofu_version: "v1.6.0"
```

With custom installation path:

```yaml
- hosts: servers
  roles:
    - role: diodonfrost.ansible-role-opentofu
      vars:
        opentofu_path: "/opt/opentofu/bin"
```

Local Testing
-------------

This project uses [Molecule](http://molecule.readthedocs.io/) to aid in the
development and testing.

To develop or test you'll need to have installed the following:

* Linux (e.g. [Ubuntu](http://www.ubuntu.com/))
* [Docker](https://www.docker.com/)
* [Python](https://www.python.org/) (including python-pip)
* [Ansible](https://www.ansible.com/)
* [Molecule](http://molecule.readthedocs.io/)
* [Libvirt](https://libvirt.org/) (If you test a system other than Linux)
* [Vagrant](https://www.vagrantup.com/downloads.html) (If you test a system other than Linux)

Testing with Docker
-------------------

```shell
# Install requirements
pip install -r requirements-dev.txt

# Test ansible role with ubuntu 24.04
molecule test

# Test ansible role with ubuntu 22.04
image=ansible-ubuntu:22.04 molecule test

# Test ansible role with alpine latest
image=ansible-alpine:latest molecule test
```

Testing with Vagrant and Libvirt
--------------------------------

```shell
# Test ansible role with FreeBSD
molecule test -s freebsd

# Test ansible role with OpenBSD
molecule test -s openbsd

# Test ansible role with Windows
molecule test -s windows
```

Supported Platforms
------------------

The role is tested and supported on the following platforms:

* EL (Enterprise Linux)
* Fedora
* Debian
* Ubuntu
* FreeBSD
* OpenBSD
* MacOSX
* Windows

License
-------

Apache Software License 2.0

Author Information
------------------

This role was created in 2023 by diodonfrost.
