[![CI](https://github.com/de-it-krachten/ansible-role-reboot/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-reboot/actions?query=workflow%3ACI)


# ansible-role-reboot

Reboot a server<br>
By default, only when reboot is pending but it can be forced


Platforms
--------------

Supported platforms

- CentOS 7
- CentOS 8
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
- name: Converge
  hosts: all
  vars:
    reboot_forced: true
  tasks:
    - name: Include role 'ansible-role-reboot'
      include_role:
        name: ansible-role-reboot
</pre></code>
