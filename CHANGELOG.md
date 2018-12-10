# Ansible Role for Bitbucket

## 2.2.0 - TBC

### Major Changes

## 2.1.0 - 2018-12-08

### Major Changes

  - Upgrade Ansible support to 2.6 or higher
  - Support both Ubuntu 16.04/18.04 and RHEL/CentOS 6/7
  - CI with yamllint, ansible-lint and ansible-playbook --syntax-check
  - CI with LXD, improve systemd support
  - Use shell only when shell functionality is required
  - Upgrade both MySQL and PostgreSQL JDBC driver
  - Simplify implementation for building Docker image

## 1.1.0 - 2017-11-23

### Major Changes

  - Install Bitbucket on Ubuntu 16.04/14.04 from source
  - Remove CentOS 7/6 support due to outdated Git provided by stock package
  - Update /etc/init.d/bitbucket with better support for running with dumb-init inside docker
  - Update test cases

## 1.0.0 - 2017-09-25

  - Ininitial release for Ansible 2.4
  - Support both Ubuntu 16.04/14.04