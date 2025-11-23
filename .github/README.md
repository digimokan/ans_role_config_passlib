# ans_role_config_passlib

Install and configure the python passlib password-hashing module.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_passlib.svg?label=release)](https://github.com/digimokan/ans_role_config_passlib/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Purpose

* Install the python [passlib](https://passlib.readthedocs.io/en/stable/lib/passlib.hash.html)
  password-hashing module.
* _passlib_ is the preferred utility used by
  [ansible.builtin.password_hash module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/password_hash_filter.html),
  which in turn is used for password creation by
  [ansible.builtin.user module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/user_module.html).
* _crypt_ is installed by default with ansible, and it's the fallback module,
  however, using it produces a playbook deprecation warning.

## Supported Operating Systems

* Ubuntu
* Arch Linux
* FreeBSD

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_passlib
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Install and configure the python passlib password-hashing module"
         ansible.builtin.include_role:
           name: ans_role_config_passlib
           public: true
   ```

## Role Options

Vars defined by this role, exported with `public: true`, for use in other roles:

  * [export](../defaults/main/export/main.yml)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_passlib/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

