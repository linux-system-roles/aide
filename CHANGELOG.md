Changelog
=========

[1.2.1] - 2025-07-02
--------------------

### Other Changes

- refactor: fix Ansible 2.19 issues (#35)

[1.2.0] - 2025-06-16
--------------------

### New Features

- feat: add Suse support (#31)

### Other Changes

- ci: Check spelling with codespell (#21)
- ci: Add test plan that runs CI tests and customize it for each role (#22)
- ci: In test plans, prefix all relate variables with SR_ (#23)
- ci: Fix bug with ARTIFACTS_URL after prefixing with SR_ (#24)
- ci: several changes related to new qemu test, ansible-lint, python versions, ubuntu versions (#25)
- ci: use tox-lsr 3.6.0; improve qemu test logging (#26)
- ci: skip storage scsi, nvme tests in github qemu ci (#27)
- ci: Bump sclorg/testing-farm-as-github-action from 3 to 4 (#28)
- ci: bump tox-lsr to 3.8.0; rename qemu/kvm tests (#29)
- ci: Add Fedora 42; use tox-lsr 3.9.0; use lsr-report-errors for qemu tests (#30)
- ci: Add support for bootc end-to-end validation tests (#32)
- ci: Use ansible 2.19 for fedora 42 testing; support python 3.13 (#33)

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

