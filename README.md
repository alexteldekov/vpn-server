# vpn-server
VPN server installation:
```
$ cat <EOF >vpn-server.yml
- hosts: vpn
  roles:
    - vpn-server
EOF
$ ansible-playbook vpn-server.yml -l hostname
```
