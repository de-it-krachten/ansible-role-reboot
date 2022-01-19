[![CI](https://github.com/de-it-krachten/ansible-role-reboot/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-reboot/actions?query=workflow%3ACI)


# ansible-role-reboot

Reboot a server
By default, only when reboot is pending but it can be forced


Platforms
--------------

Supported platforms

- CentOS 7
- CentOS 8
- RockyLinux 8
- AlmaLinux 8
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS



Role Variables
--------------
<pre><code>
# Set default for the need of a reboot
reboot_needed: false

# Should a reboot be forced
reboot_forced: false
</pre></code>


Example Playbook
----------------

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
