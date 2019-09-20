# Ansible Role: EPEL Repository

Installs the [EPEL repository](https://fedoraproject.org/wiki/EPEL) (Extra Packages for Enterprise Linux) for RHEL/CentOS.

## Role Variables
Available variables are listed below, along with default values (see defaults/main.yml):

``` yaml
# Repository name
epel_repo_name: "epel"

# EPEL metalink URL. This should not be changed normally.
epel_repo_metalink_url: "https://mirrors.fedoraproject.org/metalink?repo=epel-{{ ansible_distribution_major_version }}&arch=$basearch"

# GPG Key for the Repository. This should not be changed normally.
epel_repo_gpg_key_url: "https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-{{ ansible_distribution_major_version }}"

# EPEL repo file path. Do not add .repo extension for it.
epel_repofile_path: "/etc/yum.repos.d/epel"

# By default EPEL is installed but not enabled. Change this to true for enabling it by default
epel_repo_enabled_by_default: False
```

## Example Playbook
```yaml
- hosts: all
  vars:
    epel_repo_enabled_by_default: True
  roles:
     - { role: epel }
```

## License
[GPL-3.0](https://github.com/adfinis-sygroup.ch/ansible-role-epel/blob/master/LICENSE)

## Author Information
epel role was written by:

* Adfinis SyGroup AG | [Website](https://www.adfinis-sygroup.ch/) | [Twitter](https://twitter.com/adfinissygroup) | [GitHub](https://github.com/adfinis-sygroup)
