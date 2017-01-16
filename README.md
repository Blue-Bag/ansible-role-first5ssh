Role: SSH
========

[![Build Status](https://travis-ci.org/Blue-Bag/ansible-role-first5ssh.svg?branch=master)](https://travis-ci.org/Blue-Bag/ansible-role-first5ssh)

Configure SSH as part of the First5 provisioning set of roles


Requirements
------------
Requires SSH

Role Variables
--------------

    # SSH Settings
    # optionally change port
    `ssh_port`: "22"
    # reduce login grace time from 120 (2 minutes)
    `ssh_login_grace_time`: "20"
    # increase the server key bit encryption default=768
    `ssh_server_key_bits`: "4096"
    # control the parallelism
    `ssh_max_startups`: "10:30:100"
    #"3:50:10"

    # control forwarding
    `ssh_allow_tcp_forwarding`: "no"
    `ssh_allow_x11_forwarding`: "no"

    `ssh_allowgroups`: "anAdmin"


License
-------

MIT / BSD

Author Information
------------------

Part of the Blue-Bag First5 provision

some refs and notes:

http://www.cyberciti.biz/tips/linux-unix-bsd-openssh-server-best-practices.html

http://linux-audit.com/auditing-hardening-ssh-configurations/

some useful config vars: http://www.thelinuxguy.nl/ssh-ftp-server/how-to-secure-ssh-in-linux/


http://serverfault.com/questions/275669/ssh-sshd-how-do-i-set-max-login-attempts
has some useful IPTables rules

