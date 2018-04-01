# ansible-role-sysctl

[![Build Status](https://travis-ci.org/patchkez/ansible-role-sysctl.svg?branch=master)](https://travis-ci.org/patchkez/ansible-role-sysctl)


RHEL/CentOS and Ubuntu/Debian  -  Configure kernel parameters at runtime

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    sysctl_conf: []
    sysctl_d: []

Below is example syntax for each variable:

    sysctl_conf:
      - name: kernel.dmesg_restrict
        state: present
        value: '1'
      - name: kernel.modules_disabled
        state: present
        value: '1'

    sysctl_d:
      - file: ansible
        order: 99
        settings:
          - name: kernel.dmesg_restrict
            state: present
            value: '1'
          - name: kernel.modules_disabled
            state: present
            value: '1'

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.sysctl
          sysctl_d:
            - file: ansible
              order: 99
              settings:
                - name: kernel.dmesg_restrict
                  value: '1'
                - name: kernel.modules_disabled
                  value: '1'

## License

GPLv3

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
