# ansible-role-elrepo

Role secures-ssh by ensuring:
* fail2ban is installed and running to block IP's which maybe attempting brute force attacks
* preventing logins by users without password
* restricting root logins to key-pair only

## Requirements

None

## Role Variables

* ```sshd_config``` path to ssh daemon config files, defaults to ```/etc/ssh/sshd_config```
* ```sshd_empty_passwords``` allow/prevent remote access for users with empty passwords, defaults to ```no```
* ```sshd_root_login``` allow/prevent remote access for root user, defaults to ``` without-password```
* ```sshd_idle_timeout``` session timeout interval (in seconds) after which idle sessions will be closed
* ```sshd_allow_users``` whitelist of users permitted for remote access, unused by default
* ```sshd_enforce_protocol_2``` daemon should enforce ssh protocol 2, defaults to ```yes```


## Dependencies

* https://galaxy.ansible.com/goozbach/EPEL
(provides the fail2ban package on RHEL family OS's

## Example Playbook
```
    - hosts: servers
      roles:
        - role: gabethecabbage.secure-ssh
```
