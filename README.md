# vpn-server
VPN server installation:
```
$ cd ansible_roles_dir
$ git clone https://github.com/alexteldekov/vpn-server.git

$ cat <EOF >ansible_hosts_file
[vpn]
hostname

[vpn:vars]
ansible_python_interpreter=/usr/bin/python3
EOF

$ cat <EOF >vpn-server.yml
- hosts: vpn
  roles:
    - vpn-server
EOF
$ ansible-playbook vpn-server.yml -l hostname
```
