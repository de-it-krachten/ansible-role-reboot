[![CI](https://github.com/de-it-krachten/ansible-role-reboot/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-reboot/actions?query=workflow%3ACI)


# ansible-role-reboot

Reboot a server
By default, only when reboot is pending but it can be forced


## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- OracleLinux 8
- AlmaLinux 8
- AlmaLinux 9
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 35
- Fedora 36

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Set default for the need of a reboot
reboot_needed: false

# Should the reboot be postponed (and not be executed by this role)
reboot_postponed: false

# Should a reboot be forced
reboot_forced: false

# Amount of seconds to wait for host to become active before trowing an error
reboot_timeout: 300
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'reboot'
  hosts: all
  vars:
    reboot_forced: True
  tasks:
    - name: Include role 'reboot'
      include_role:
        name: reboot
</pre></code>
