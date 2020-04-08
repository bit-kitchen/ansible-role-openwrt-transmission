ansible-role-openwrt-transmission
=================================

[![Ansible Role: bit_kitchen.openwrt_transmission](https://img.shields.io/ansible/role/47726.svg)](https://galaxy.ansible.com/bit_kitchen/openwrt_transmission)
[![Build Status: bit-kitchen/ansible-role-openwrt-transmission](https://travis-ci.org/bit-kitchen/ansible-role-openwrt-transmission.svg?branch=master)](https://travis-ci.org/bit-kitchen/ansible-role-openwrt-transmission)

```sh
ansible-galaxy install bit_kitchen.openwrt_transmission
```

Configure OpenWrt for Transmission.

Requirements
------------

None.

Role Variables
--------------

Variable                      | Default     | Comment
----------------------------- | ----------- | -------
transmission_luci             | yes         | Install transmission luci app
transmission_config_dir       | (undefined) | Transmission config dir. <br> Defaults to the first mount point of external filesystems.
transmission_download_dir     | {{ transmission_config_dir }}/done | Download dir of transmission
transmission_incomplete_dir   | (undefined) | Incomplete dir of transmission. <br> Leave undefined to disable incomplete dir.
transmission_watch_dir        | (undefined) | Watch dir of transmission. <br> Leave undefined to disable watch dir.
transmission_rpc_enabled      | true        | Enable transmission web interface
transmission_rpc_bind_address | 0.0.0.0     | Transmission web interface bind address
transmission_rpc_port         | 9091        | Transmission web interface bind port

Dependencies
------------

* `gekmihesg.openwrt`
* `bit_kitchen.openwrt_storage`

Example Playbook
----------------

```yml
- hosts: openwrt
  remote_user: root
  gather_facts: no
  roles:
  - bit_kitchen.openwrt_transmission
```

License
-------

[MIT](LICENSE)

Author Information
------------------

[bit.kitchen](https://github.com/bit-kitchen)
