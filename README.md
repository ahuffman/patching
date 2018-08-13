# ahuffman.patching

An Ansible Role to perform automated patching of systems.  The Role checks to see if services need restarting and also if the system needs a reboot due to patching.

# Role Variables

| Variable Name | Required | Description | Default Value | Variable Type |
| --- | :---: | --- | --- | :---: |
| patch_display_patch_output | no | Whether or not to display output results of patching procedure | True | boolean |
| patch_reboot_message | no | "Rebooting due to patching." | string |


# Example Playbook
```yaml
    - hosts: "all"
      tasks:
        - name: "Patch Servers"
          include_role:
            name: "ahuffman.patching"
          vars:
            patch_display_patch_output: False
```
# License
[MIT](LICENSE)

# Author Information
[Andrew J. Huffman](https://github.com/ahuffman)
