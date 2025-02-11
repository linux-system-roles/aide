Changelog
=========

[1.1.1] - 2025-02-11
--------------------

### Bug Fixes

- fix: aide --check should not report changed (#19)

### Other Changes

- refactor: Changed ansible_db_template to ansible_config_template (#18)

[1.1.0] - 2025-01-31
--------------------

### New Features

- feat: ensure role works on ostree systems (#15)

### Other Changes

- ci: ansible-plugin-scan is disabled for now (#11)
- ci: bump ansible-lint to v25; provide collection requirements for ansible-lint (#14)

[1.0.0] - 2025-01-09
--------------------

### New Features

- feat: Allow setup aide inside of cron job (#7)

### Other Changes

- ci: Use Fedora 41, drop Fedora 39 (#5)
- ci: Use Fedora 41, drop Fedora 39 - part two (#6)
- test: add cleanup for cron test; fix formatting (#9)

[0.0.1] - 2024-11-12
--------------------

### New Features

- feat: Import code for role (#3)

### Other Changes

- refactor: Use vars/RedHat_N.yml symlink for CentOS, Rocky, Alma wherever possible (#1)

