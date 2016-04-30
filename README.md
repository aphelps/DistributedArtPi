# Distribute Art Raspberry Pi setup



There are several ansible roles that need to be installed:
``` 
ansible-galaxy install -r install_roles.yml
```

An ssh public key needs to be provided.  To generate this:
```
sh-keygen -t rsa -f distributed_art.id_rsa
```

Setup your hosts and wifi settings:

```cp hosts.example hosts
cp wpa_supplicant.conf.example wpa_supplicant.conf
```

Edit the `wpa_supplicant.conf` and `hosts` files.

Deploy using [ansible](http://www.ansible.com).

```
ansible-playbook playbook.yml -i hosts --ask-pass --sudo -c paramiko
```

After the first successful run ssh keys should be installed and the --ask-pass option will not be needed on future executions
