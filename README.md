Makes and starts servise files for [https://github.com/strizhechenko/netutils-linux][netutils-linux] or your own scripts, that must be started after reboot.
Example:

```yaml
nettune:
  - name: autorps
  - name: maximize-cpu-freq
    templated: false
  - name: IntInfo
    exec_start: '/usr/sbin/ip a show dev'
    descritpion: 'Show info about interface'
    autostart: true
```
you can choose interfases:
```yaml
nettune_interfaces: ['em1', 'em2']
```

or leave default:
```yaml
nettune_interfaces: ['{{ ansible_default_ipv4.interface }}']
```

### Be careful don't make it 'autostart', before testing!
