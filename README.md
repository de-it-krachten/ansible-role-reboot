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

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- Red Hat Enterprise Linux 10<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- RockyLinux 10
- OracleLinux 8
- OracleLinux 9
- OracleLinux 10
- AlmaLinux 8
- AlmaLinux 9
- AlmaLinux 10
- SUSE Linux Enterprise 15<sup>1</sup>
- SUSE Linux Enterprise 16<sup>1</sup>
- openSUSE Leap 15
- openSUSE Leap 16
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Debian 13 (Trixie)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Fedora 42
- Fedora 43

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

# Port to check for in async mode
reboot_port_check: 22
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'reboot'
  hosts: all
  become: 'yes'
  vars:
    molecule_driver: '{{ lookup(''env'', ''MOLECULE_DRIVER_NAME'') }}'
    reboot_forced: true
  tasks:
    - name: Include role 'reboot'
      ansible.builtin.include_role:
        name: reboot
</pre></code>
