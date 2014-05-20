Stouts.postfix
==============

[![Build Status](https://travis-ci.org/Stouts/Stouts.postfix.png)](https://travis-ci.org/Stouts/Stouts.postfix)

Ansible role which manage postfix

#### Variables

```yaml
postfix_enabled: yes # The role is enabled

postfix_myhostname: "{{inventory_hostname}}"
postfix_myorigin: example.com
postfix_smtpd_use_tls: yes
postfix_smtp_sasl_auth_enable: yes
postfix_smtp_sasl_password_maps: "hash:/etc/postfix/sasl_passwd"
postfix_smtp_sasl_security_options: "noanonymous"
postfix_smtp_tls_cafile: "etc/ssl/certs/Thawte_Premium_Server_CA.pem"
postfix_mydomain: "{{inventory_hostname}}"
postfix_mail_type: client
postfix_mynetworks: "127.0.0.0/8" # network mask of what machines on the network can use this postfix mail relayer
postfix_smtp_sasl_user: "{{ansible_ssh_user}}"
postfix_smtp_sasl_passwd: ""
postfix_relayhost: ""
postfix_relayhost_port: 25
postfix_inet_interfaces: loopback-only
```

#### Usage

Add `Stouts.postfix` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.postfix

  vars:
    postfix_myhostname: test.com

```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.postfix/issues)!
