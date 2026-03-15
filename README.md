[![CI](https://github.com/de-it-krachten/ansible-role-awx_cli/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-awx_cli/actions?query=workflow%3ACI)


# ansible-role-awx_cli

Installs the AWX CLI aka awxkit



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- Red Hat Enterprise Linux 10<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- RockyLinux 10
- OracleLinux 8
- OracleLinux 9
- OracleLinux 10
- AlmaLinux 8
- AlmaLinux 9
- AlmaLinux 10
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Debian 13 (Trixie)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Fedora 42
- Fedora 43

Note:
<sup>1</sup> : no automated testing is performed on these platforms


## Role Variables
### defaults/main.yml
<pre><code>
# Awxkit / AWX cli version
awx_cli_version: 24.6.1

# List of pypi packages to install
awx_cli_packages:
  - "awxkit=={{ awx_cli_version }}"
  - "pyyaml"

# Virtual environment base packages
awx_cli_venv_base_packages:
  - pip
  - wheel
  - "setuptools<82"

# venv root
awx_cli_venv_path: /usr/local/venv/awxkit

# Python version to use
awx_cli_venv_python: /usr/bin/python3.11
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'awx_cli'
  hosts: all
  become: 'yes'
  tasks:
    - name: Include role 'awx_cli'
      ansible.builtin.include_role:
        name: awx_cli
</pre></code>
