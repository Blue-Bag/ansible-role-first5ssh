Role: SSH
========

[![Build Status](https://travis-ci.org/Blue-Bag/ansible-role-first5ssh.svg?branch=main)](https://travis-ci.org/Blue-Bag/ansible-role-first5ssh)

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

Hardening
----------
  * Consider hardening SSH configuration [SSH-7408]
    - Details  : ClientAliveCountMax (3 --> 2)
      https://cisofy.com/controls/SSH-7408/
      http://go2linux.garron.me/linux/2011/02/limit-idle-ssh-sessions-time-avoid-unattended-ones-clientaliveinterval-clientalivecoun/

  * Consider hardening SSH configuration [SSH-7408]
    - Details  : LogLevel (INFO --> VERBOSE)
      https://cisofy.com/controls/SSH-7408/

  * Consider hardening SSH configuration [SSH-7408]
    - Details  : MaxAuthTries (6 --> 2)
      https://cisofy.com/controls/SSH-7408/

  * Consider hardening SSH configuration [SSH-7408]
    - Details  : MaxSessions (10 --> 2)
      https://cisofy.com/controls/SSH-7408/

  * Consider hardening SSH configuration [SSH-7408]
    - Details  : PermitRootLogin (WITHOUT-PASSWORD --> NO)
      https://cisofy.com/controls/SSH-7408/

  * Consider hardening SSH configuration [SSH-7408]
    - Details  : Port (22 --> )
      https://cisofy.com/controls/SSH-7408/

  * Consider hardening SSH configuration [SSH-7408]
    - Details  : TCPKeepAlive (YES --> NO)
      https://cisofy.com/controls/SSH-7408/

  * Consider hardening SSH configuration [SSH-7408]
    - Details  : UseDNS (YES --> NO)
      https://cisofy.com/controls/SSH-7408/

  * Consider hardening SSH configuration [SSH-7408]
    - Details  : UsePrivilegeSeparation (YES --> SANDBOX)
      https://cisofy.com/controls/SSH-7408/
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
