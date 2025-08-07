Ansible Role Helm
=========

[![Molecule Test](https://github.com/x86-39/ansible_role_helm/actions/workflows/molecule.yml/badge.svg)](https://github.com/x86-39/ansible_role_helm/actions/workflows/molecule.yml)

This is an Ansible role to install and [helm](https://helm.sh).

Requirements
------------
These platforms are supported:
These platforms are supported:
- Ubuntu 22.04  
- Ubuntu 24.04  
- Debian 12  
- EL 9 (Tested on Rocky Linux 9)  
- EL 10 (Tested on Rocky Linux 10)  
- Fedora 42  
- openSUSE Leap 16.0 (BETA, but I'm targeting this)  

<!--
- List hardware requirements here  
-->

Role Variables
--------------

Variable | Default | Description
--- | --- | ---
`helm_install_with_package` | `true` | Whether to install helm with the package manager when available. Falls back to archive installation if not available.
`helm_archive_version` | `v3.17.4` | Version of helm to install when installing from archive
<!--
`variable` | `default` | Variable example
`long_variable` | See [defaults/main.yml](./defaults/main.yml) | Variable referring to defaults
`distro_specific_variable` | See [vars/debian.yml](./vars/debian.yml) | Variable referring to distro-specific variables
-->

Dependencies
------------
<!-- List dependencies on other roles or criteria -->
None

Example Playbook
----------------

```yaml
    - role: "x86_39.helm"
      tags: ['x86_39', 'helm', 'setup']

```

License
-------

MIT

Author Information
------------------

- Jasmijn Emilia Rosalina Knoope (@x86-39)

Role Testing
------------

This repository comes with Molecule that run in Podman on the supported platforms.
Install Molecule by running

```bash
pip3 install -r requirements.txt
```

Run the tests with

```bash
molecule test
```

These tests are automatically ran by GitHub Actions on push. If the tests are successful, the role is automatically published to Ansible Galaxy.
