# Ansible Role: Common

[![Build Status](https://img.shields.io/travis/polymimetic/ansible-role-common.svg?style=flat-square)](https://travis-ci.org/polymimetic/ansible-role-common)
[![Release](https://img.shields.io/github/tag/polymimetic/ansible-role-common.svg?style=flat-square)](https://github.com/polymimetic/ansible-role-common/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-polymimetic.common-blue.svg?style=flat-square)](https://galaxy.ansible.com/polymimetic/common/)

Base role to install some common packages and utilites.

## Requirements

No requirements.

## Dependencies

No dependencies.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    common_apt_upgrade_type: safe

The type of upgrade to perform before installing apt packages. Valid values include: yes, no, safe, full and dist.

    common_apt_upgrade_force: no

If yes, forces upgrade

    common_apt_cache_time: 86400

The time (in seconds) to set the current apt cache. Current default is set for one day.

    common_apt_upgrade: yes

Determines if apt should upgrade packages.

    common_apt_update: yes

Determines if the apt cache should be updated.

    common_apt_remove_packages: []

Array of packages to purge from system.

    common_apt_state: present

Determines the state for packages installed on the system. Available values are `present` or `latest`.

    common_apt_dependencies:
      - software-properties-common
      - git
      - ssh
      - curl
      - nano
      - sudo
      - wget

Array of common apt package dependencies. These packages should be installed before all others.

    common_apt_packages_default:
      - apt-transport-https
      - build-essential
      - unattended-upgrades
      - dos2unix
      - gcc
      - htop
      - libglib2.0-dev
      - libmcrypt4
      - libpcre3-dev
      - make
      - mcrypt
      - ntp
      - pwgen
      - pv
      - re2c
      - supervisor
      - whois
      - vim

Array of default apt packages.

    common_apt_packages_archive:
      - arj
      - bzip2
      - cabextract
      - gzip
      - mpack
      - p7zip-full
      - p7zip-rar
      - rar
      - sharutils
      - tar
      - unace
      - unrar
      - unzip
      - uudeview
      - zip

Array of archive apt packages. These packages should be able to zip and unzip most files and folders.

    common_apt_packages_disk:
      - cifs-utils
      - exfat-utils
      - exfat-fuse
      - ntfs-3g

Array of disk utility apt packages. These packages should be able to read most Windows-oriented SD cards and file systems.

    common_apt_add_packages: "{{ common_apt_packages_default + common_apt_packages_archive + common_apt_packages_disk }}"

Array of base apt packages to install.

    common_apt_custom_packages: []

Array of custom apt packages to install.

## Example Playbook

To run the role, include it as follows:

    - hosts: all
      roles:
         - { role: polymimetic.common, x: 42 }

## Credits

This role takes inspiration from the following Ansible roles:

- [darkraiden.ansible-base](https://github.com/darkraiden/ansible-role-base)
- [bbatsche.Base](https://github.com/bbatsche/Ansible-Common-Role)
- [coaxial.base](https://github.com/coaxial/ansible-role-base)
- [Ilyes512.Base](https://github.com/Ilyes512/ansible-role-base)
- [fubarhouse.commons](https://github.com/fubarhouse/ansible-role-commons)
- [viasite-ansible.common](https://github.com/viasite-ansible/ansible-role-common)
- [fabschurt.ubuntu-base](https://github.com/fabschurt/ansible-role-ubuntu-base)
- [fretscha.first-five-minutes](https://github.com/fretscha-ansible/ansible-role-first-five-minutes)
- [kosssi.apt](https://github.com/kosssi/ansible-role-apt)
- [manala.apt](https://github.com/manala/ansible-role-apt)
- [antonchernik.common](https://github.com/antonchernik/ansible-role-common)
- [stuvusIT.common](https://github.com/stuvusIT/common)
- [Stouts.foundation](https://github.com/Stouts/Stouts.foundation)
- [kbrebanov.common](https://github.com/kbrebanov/ansible-common)

## License

This software package is licensed under the [MIT License](https://opensource.org/licenses/MIT). See the [LICENSE](./LICENSE) file for details.

## Author Information

This role was created in 2017 by [Polymimetic](https://github.com/polymimetic).

* ansible-role-common generated using [ansible-role-skeleton](https://github.com/polymimetic/ansible-role-skeleton)