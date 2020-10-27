# Symbol Network Deployment With Ansible

This repo defines some base scripts for how you can use the [symbol-bootstrap](https://github.com/nemtech/symbol-bootstrap) tool to deploy a custom network configuration to multiple nodes to form a larger network.

Keep in mind, these only have been tested on Ubuntu 20.04 machines.  In the future, we will provide support via Ansible roles for other OSes.

## Usage

It's recommended that you modify inventories/prod/hosts with your specific network parameters.  This way, you can specify different inventories for different networks.

In `preset/`, make sure to fill the contents of `preset/custom_preset.yml` with your preset before running.

```sh
ansible-playbook <script>.yml -i inventories/prod/hosts 
```

### deploy.yml
This is used to initially setup a network, where dependencies are installed.  It should be run only once. 

### run.yml
Runs `symbol-bootstrap run` on all machines, thereby running the nodes.

### run.yml
Runs `symbol-bootstrap stop` on all machines, stopping any the instance.