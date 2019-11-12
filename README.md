# Ansible Rsyslog
Role to install an configure Rsyslog with Ansible.

## Requirements
None

## Tested plateform
* Debian 9 (Stretch)
* Debian 10 (Buster)

## Role variables
Those variables are used to determine who is the owner of the files created by rsyslog, and to define the associated rights.
```yml
rsyslog_file_owner: root
rsyslog_file_group: adm
rsyslog_file_create_mode: 0640
rsyslog_dir_create_mode: 0755
rsyslog_umask: 0022
```
Path to the logs files
```yml
rsyslog_work_directory: /var/spool/rsyslog
rsyslog_include_config: /etc/rsyslog.d/*.conf
rsyslog_auth_log: /var/log/auth/auth.log
rsyslog_daemon_log: /var/log/daemon/daemon.log
rsyslog_kern_log: /var/log/kern/kern.log
rsyslog_lpr_log: /var/log/lpr/lpr.log
rsyslog_mail_log: /var/log/mail/mail.log
rsyslog_mail_info_log: /var/log/mail/mail.info
rsyslog_mail_warn_log: /var/log/mail/mail.warn
rsyslog_mail_err_log: /var/log/mail/mail.err
rsyslog_debug_log: /var/log/debug-d/debug.log
rsyslog_messages_log: /var/log/messages-d/messages.log
```

## Example(s)
```yml
---
- hosts: somehost
  roles:
    - supertarto.rsyslog
  vars:
    rsyslog_auth_log: /var/log/auth/auth.log
    rsyslog_daemon_log: /var/log/daemon/daemon.log
    rsyslog_kern_log: /var/log/kern/kern.log


```
## Installation
```
ansible-galaxy install supertarto.rsyslog
```
## License
GPL V3.0
