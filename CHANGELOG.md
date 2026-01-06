Changelog
=========

[1.2.4] - 2026-01-06
--------------------

### Other Changes

- ci: bump actions/checkout from 5 to 6 (#58)
- ci: bump actions/upload-artifact from 5 to 6 (#59)
- docs: fix copyright in license (#60)

[1.2.3] - 2025-12-17
--------------------

### Bug Fixes

- fix: support new config file options, expose aide_version (#54)

### Other Changes

- ci: bump gha checkout from v5 to v6 (#55)
- ci: add qemu tests for Fedora 43, drop Fedora 41 (#56)

[1.2.2] - 2025-11-17
--------------------

### Bug Fixes

- fix: cannot use community-general version 12 - no py27 and py36 support (#52)

### Other Changes

- ci: rollout several recent changes to CI testing (#38)
- ci: support openSUSE Leap in qemu/kvm test matrix (#39)
- ci: use the new epel feature to enable EPEL for testing farm (#40)
- ci: use tox-lsr 3.12.0 for osbuild_config.yml feature (#42)
- ci: use JSON format for __bootc_validation (#43)
- ci: bump actions/checkout from 4 to 5 (#44)
- ci: bump actions/github-script from 7 to 8 (#45)
- ci: bump actions/upload-artifact from 4 to 5 (#48)
- ci: use versioned upload-artifact instead of master; bump codeql-action to v4; bump upload-artifact to v5 (#49)
- ci: bump tox-lsr to 3.13.0 (#50)
- ci: bump tox-lsr to 3.14.0 - this moves standard-inventory-qcow2 to tox-lsr (#51)

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

