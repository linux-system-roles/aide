# AIDE

[![ansible-lint.yml](https://github.com/linux-system-roles/aide/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/linux-system-roles/aide/actions/workflows/ansible-lint.yml) [![ansible-test.yml](https://github.com/linux-system-roles/aide/actions/workflows/ansible-test.yml/badge.svg)](https://github.com/linux-system-roles/aide/actions/workflows/ansible-test.yml) [![markdownlint.yml](https://github.com/linux-system-roles/aide/actions/workflows/markdownlint.yml/badge.svg)](https://github.com/linux-system-roles/aide/actions/workflows/markdownlint.yml) [![shellcheck.yml](https://github.com/linux-system-roles/aide/actions/workflows/shellcheck.yml/badge.svg)](https://github.com/linux-system-roles/aide/actions/workflows/shellcheck.yml) [![tft.yml](https://github.com/linux-system-roles/aide/actions/workflows/tft.yml/badge.svg)](https://github.com/linux-system-roles/aide/actions/workflows/tft.yml) [![tft_citest_bad.yml](https://github.com/linux-system-roles/aide/actions/workflows/tft_citest_bad.yml/badge.svg)](https://github.com/linux-system-roles/aide/actions/workflows/tft_citest_bad.yml) [![woke.yml](https://github.com/linux-system-roles/aide/actions/workflows/woke.yml/badge.svg)](https://github.com/linux-system-roles/aide/actions/workflows/woke.yml)

This is an ansible role that installs and configures the [Advanced Intrusion Detection Environment (AIDE)](https://aide.github.io). For Day 2 tasks it can run integrity checks and update the AIDE database.

## What does this role do for you?

* It ensures that the `aide` package is installed on the remote nodes
* As an optional task it can generate the `/etc/aide.conf` file and template it out to the remote nodes
* It initializes the AIDE database
* The AIDE databases from the remote nodes are stored in a central directory on the controller node
* It runs AIDE integrity checks on the remote nodes
* It updates the AIDE databases and stores them on the controller node

## What does this role not do for you?

* It does not explain how to create a good AIDE configuration that suits your requirements; that task remains for you to accomplish

## Requirements

This role has no special requirements as it uses `ansible.builtin` modules
only.

## Role Variables

### aide_db_template

This variable takes a string to specify a path where the custom template for aide.conf is located.

To be sure that everething is correct, template needs to start with following snippet:

``` jinja
{{ ansible_managed | comment }}
{{ "system_role:aide" | comment(prefix="", postfix="") }}
```

Default: `null`

Type: `string`

### aide_db_fetch_dir

This variable takes a string to specify the directory on the Ansible Control
Node (ACN) where the role will store the AIDE database fetched from the remote
nodes. The default value is `files` which is expected to be a directory in the
same directory as the playbook.

In case you like to store the fetched AIDE database files somewhere else you
need to specify a different path here.

Default: `files`

Type: `string

### aide_init

Initializes the AIDE database.

Default: `false`

Type: `bool`

### aide_fetch_db

Fetches database from the remote nodes to store it on the controller node

Default: `false`

Type: `bool`

### aide_check

Runs an integrity check on the remote nodes

Default: `false`

Type: `bool`

### aide_update

Updates the AIDE database and stores it on the controller node

Default: `false`

Type: `bool`

### aide_cron_check

If set to `true`, configures periodic cron check for aide
If set to `false`, removes the periodic cron check

Default: `null`

Type: `bool`

### aide_cron_interval

Set check interval for cron

``` yaml
# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  *
```

Default: `0 12 * * *`

Type: `string`

## Example Playbook

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

```yaml
# SPDX-License-Identifier: MIT
---
- name: Example aide role invocation
  hosts: targets
  tasks:
    - name: Include role aide
      vars:
        aide_db_fetch_dir: files
        aide_install: true
        aide_generate_config: true
        aide_init: true
        aide_check: false
        aide_update: false
      ansible.builtin.include_role:
        name: linux-system-roles.aide
```

More examples can be found in the [`examples/`](examples) directory.

## License

MIT.

## Author Information

* Radovan Sroka
* Joerg Kastning
* Based on [Tronde/aide](https://github.com/Tronde/aide) ansible role
