# OCP static deployment
### Warning: This is beta version !!!  
I try writing ansible clearly and simply as I can for everyone.
## setup
- Config all variables in vars folder
- Put your pull secret to folder files/pull-secret.json

## How to used
- Check port firewall is open
\# ansible-playbook check_ports_open.yml

- Check connection to whitelist url
\# ansible-playbook check_whitelist_url.yml

- Generate ignition file and iso for install OCP
\# ansible-playbook setup_ocp_static.yml

Note : When you run setup_ocp_static.yml all file will download to files directory

## Tested
- deploy ocp 4.2.16 bare-metal ==> SUCCESS
- deploy on VMware ==> Developing and Testing

## Tree
ocp-static-deploy/
├── ansible.cfg
├── check_ports_open.yml
├── check_whitelist_url.yml
├── clear_all.sh
├── files
│   └── pull-secret.json
├── inventory
├── setup_ocp_static.yml
├── templates
│   ├── ifcfg-interface.j2
│   ├── install-config-bare-metal.yml.j2
│   └── install-config-vsphere.yaml.j2
└── vars
    ├── ip_ports.yml
    ├── nodes_vars.yml
    ├── openshift_vars.yml
    ├── packages_vars.yml
    └── whitelist_url.yml

3 directories, 15 files


License
----

MIT

**Free Software and Bugs, Hell Yeah!**

