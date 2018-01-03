# ansible-role-elrepo

Role secures-ssh by ensuring:
* fail2ban is installed and running to block IP's which maybe attempting brute force attacks
* preventing logins by users without password
* restricting root logins to key-pair only

## Requirements

None

## Role Variables

```sshd_config``` provides the path to the ssh server config files and defaults to ```/etc/ssh/sshd_config```

## Dependencies

* https://galaxy.ansible.com/goozbach/EPEL
(provides the fail2ban package on RHEL family OS's

## Example Playbook
```
    - hosts: servers
      roles:
        - role: gabethecabbage.secure-ssh
```
