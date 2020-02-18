## Spin up a k8s cluster using Vagrant
This repository creates 3 local VMs:

- 1 Master node 
- 2 Worker nodes

### Pre-requisites 

- VirtualBox 6.0 or higher, Download from [here](https://www.virtualbox.org/wiki/Downloads)
- Vagrant, Download from [here](https://www.vagrantup.com/downloads.html)
- git 

## Usage
```
git clone git@github.com:Airbox/local-kubernetes.git 
cd local-kubernetes
vagrant up
```

## How to login
```
1- vagrant status  # Shows the status of the VMS
eg:
vagrant status
Current machine states:

kmaster                   running (virtualbox)
kworker1                  running (virtualbox)
kworker2                  running (virtualbox)
```	
2- vagrant ssh kmaster # To login to the master node
````

### Or using ssh

vagrant creates a hidden directory .vagrant where the ssh keys are stored 

ssh -i .vagrant/machines/kmaster/virtualbox/private_key vagrant@172.42.42.100
```

## Networking:

This setup uses the networking as below :
- kmaster : 172.42.42.100
- kworker1: 172.42.42.101
- kworker2: 172.42.42.102

## Note:
It is recommended to use ```vagrant suspend``` before switch off your laptop to save the configuration
To completely destroy the VMS:
``` vagrant destroy -f ```

For further details about vagrant commands, please visit the [Getting Started](https://www.vagrantup.com/intro/getting-started/index.html)
