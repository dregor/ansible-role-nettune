Makes and starts servise files for [netutils-linux][netutils-linux] or your own scripts, that must be started after reboot.
Example:

```yaml
nettune:
  - name: autorps
    interfaces: 
      - "{{ ansible_default_ipv4.interface }}" 
      - "em2"
    autostart: false
  - name: maximize-cpu-freq
    templated: false
  - name: something
    exec_start: '/path/to/some/thing/some_exec_file --key1 --key2 --templated_key'
    descritpion: 'Seper descritpion'
```
### Be careful don't make it 'autostart', before testing!