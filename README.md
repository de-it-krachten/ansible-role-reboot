[![CI](https://github.com/de-it-krachten/ansible-role-reboot/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-reboot/actions?query=workflow%3ACI)


# ansible-role-reboot

Reboot a server
By default, only when reboot is pending but it can be forced



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Fedora 39
- Fedora 40

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

# Amount of seconds to wait for host to become active before throwing an error
reboot_timeout: 300

# Reboot in async mode
reboot_async: false
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'reboot'
  hosts: all
  become: 'yes'
  vars:
    reboot_forced: true
  tasks:
    - name: Include role 'reboot'
      ansible.builtin.include_role:
        name: reboot
</pre></code>
