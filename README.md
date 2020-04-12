# Ansible Role for Bitbucket

[![Travis](https://img.shields.io/travis/com/kube-cloud/ansible-role-bitbucket/master?style=flat)](https://travis-ci.com/kube-cloud/ansible-role-bitbucket)
[![GitHub release](https://img.shields.io/github/release/kube-cloud/ansible-role-bitbucket.svg)](https://github.com/kube-cloud/ansible-role-bitbucket)
[![GitHub license](https://img.shields.io/github/license/kube-cloud/ansible-role-bitbucket.svg)](https://github.com/kube-cloud/ansible-role-bitbucket/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/ansible/role/d/46827.svg?style=flat)](https://galaxy.ansible.com/kube-cloud/bitbucket)

Ansible Role for Atlassian Bitbucket Installation.

<a href="https://www.kube-cloud.com/"><img width="300" src="https://kube-cloud.com/images/branding/logo/kubecloud-logo-single_writing_horizontal_color_300x112px.png" /></a>
<a href="https://www.redhat.com/fr/technologies/management/ansible"><img width="200" src="https://getvectorlogo.com/wp-content/uploads/2019/01/red-hat-ansible-vector-logo.png" /></a>
<a href="https://www.atlassian.com/software/bitbucket"><img width="120" src="https://confluence.atlassian.com/bitbucket/files/877358733/946613493/12/1558311280599/BitbucketLogo180x200.png" /></a>

# Supported Version

* Atlassian Bitbucket 6+

# Supported OS

* CentOS 6/7
* RedHat 6/7
* Ubuntu Trusty/Xenial/Bionic

# Depend On

* jetune.java (Java 1.8+)

# Usage

* Install Role ``` ansible-galaxy install jetune.bitbucket ```
* use in your playbook
```
---

- hosts: all
  become: true
  tasks:

    - name: "Include bitbucket role"
      import_role:
        name: ansible-role-bitbucket
      vars:
        bitbucket_download:
          url: "https://product-downloads.atlassian.com/software/stash/downloads/atlassian-bitbucket-6.10.1.tar.gz"
          dest: "/var/cache/ansible/atlassian-bitbucket-6.10.1.tar.gz"
          checksum: "sha1:9e34533bc421f53c4428b74ac4c3fe702ac65131"
        mysql_jdbc_download:
          url: "https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.48.tar.gz"
          dest: "/var/cache/ansible/mysql-connector-java-5.1.48.tar.gz"
          checksum: "sha1:a8067480d7d7e4a975771e08b48b64de18837341"
        postgresql_jdbc_download:
          url: "https://jdbc.postgresql.org/download/postgresql-42.2.10.jar"
          dest: "/var/cache/ansible/postgresql-42.2.10.jar"
          checksum: "sha1:338af492789fd198dbd52735a22b1946030ecc96"
        bitbucket_owner: "bitbucket"
        bitbucket_group: "bitbucket"
        bitbucket_shell: "/usr/sbin/nologin"
        bitbucket_create_home: false
        bitbucket_owner_system: true
        bitbucket_catalina: "/opt/atlassian/bitbucket"
        bitbucket_home: "/var/atlassian/applicationdata/bitbucket"
        bitbucket_jvm_minimum_memory: "256m"
        bitbucket_jvm_maximum_memory: "512m"
        bitbucket_catalina_connector_scheme: "https"
        bitbucket_catalina_connector_secure: "true"
        bitbucket_catalina_context_path: "/"
        bitbucket_catalina_connector_port: 8080
        bitbucket_properties_file_generation: true
        bitbucket_properties_file_name: "bitbucket.properties"
        bitbucket_extra_properties:
          - key: "plugin.auth-crowd.sso.enabled"
            value: "false"
          - key: "avatar.gravatar.default"
            value: "mm"
          - key: "avatar.max.size"
            value: 1048576
          - key: "db.pool.size.idle"
            value: 0
          - key: "db.pool.size.max"
            value: 80
          - key: "jmx.enabled"
            value: true
          - key: "page.max.branches"
            value: 100
          - key: "page.max.commits"
            value: 100
          - key: "password.reset.validity.period"
            value: 4320
