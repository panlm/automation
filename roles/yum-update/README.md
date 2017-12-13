# ansible-role-yum-update

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-yum-update.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-yum-update)

RHEL/CentOS - Package updates and permission settings

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    yum_update: True
    yum_update_disable_gpg_check: False
    yum_update_disablerepo: []
    yum_update_enablerepo: []
    yum_update_exclude: ''
    yum_update_perms: []
    yum_update_update_cache: False
    yum_update_validate_certs: True

Additional variables not defined by default:

    yum_update_conf_file: /etc/yum-custom.conf
    
## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.yum-update
          yum_update_enablerepo:
            - epel
          yum_update_perms:
            - package: mlocate
              state: absent
              permissions: []
            - package: util-linux
              state: latest
              permissions:
                - path: /bin/su
                  mode: 755
          yum_update_update_cache: True

## License

GPLv3

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
