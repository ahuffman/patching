![Ansible Role](https://img.shields.io/ansible/role/d/30634)

# ahuffman.patching

An Ansible Role to perform automated patching of systems.  The Role checks to see if services need restarting and also if the system needs a reboot due to patching.

# Role Variables
| Variable Name | Required | Description | Default Value | Variable Type |
| --- | :---: | --- | --- | :---: |
| patch_display_patch_output | yes | Whether or not to display output results of patching procedure | True | boolean |
| patch_reboot_message | no | Message to pass to the reboot module when a reboot is required due to patching activities. | "Rebooting due to patching." | string |
| patch_pkgs | no | List of specific packages to patch. **Patches all packages by default.** | ["*"] | list |
| patch_never_reboot | no | To ensure a system never reboots if a reboot is required post patching, set to True | False | boolean |
| patch_never_restart_svc | no | To ensure services never restart if required post patching, set to True | False | boolean |

# Example Playbook
```yaml
    - hosts: "all"
      tasks:
        - name: "Patch Servers"
          include_role:
            name: "ahuffman.patching"
          vars:
            patch_display_patch_output: False
            patch_pkgs:
              - "yum"
              - "httpd"
              - "ansible"
            patch_never_reboot: True
            patch_never_restart_svc: True
```
# License
[MIT](LICENSE)

# Author Information
[Andrew J. Huffman](https://github.com/ahuffman)
