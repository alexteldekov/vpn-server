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
Based on https://github.com/Nyr/openvpn-install

Do not forget to add usernames and passwords to `/etc/ipsec.secrets`!
Then run `ipsec restart` to apply them.

## OpenFire

`open http://jabber.$DOMAIN.TLD:9090`

* hostname = jabber.$DOMAIN.$TLD, embedded DB.
* Users/Groups - Users - Create New User
* Plugins - Plugin Admin - Available Plugins - Kraken IM Gateway (+)
* Server - Gateways - Transports - [V] ICQ - Options - Encoding: Windows-1251
* Server - Gateways - Registrations - Add a new registration
