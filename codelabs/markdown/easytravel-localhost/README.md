summary: Deploy Easytravel @ localhost
id: deploy-easytravel-at-localhost
categories: DEM, localhost, easytravel
tags: DEM, localhost, easytravel
status: Published
authors: sergio.hinojosa

# Deploying Easytravel at Localhost

## Introduction 
Duration: 3

for learning, and playing around there is nothing better than having a separate VM that you can break. This can be either an instance in a cloud provider or a virtual machine @ localhost. On your working station you can use a docker container with an ubuntu image or https://multipass.run/. Multipass is a great way to instantiate Ubuntu VMs and runs on Linux, Mac and Windows. it's made by the Ubuntu team highly optimized. 

## Multipass Comands
Duration: 5

### Download & Install
Download multipass and install it depending on your OS https://multipass.run/

### Show the help
```bash
multipass -h
```

###  Start a VM with x size
```bash
multipass launch --name <vm-name> --mem 4G --disk 10G --cpus 2
```

###  Start the VM	
```bash
multipass start <vm-name>
```

### Stop the VM	
```bash
multipass stop <vm-name>
```
### List VMS
```bash
multipass list
```

### Shell into the VM
> you can also shell into the vm with the ip but you need to set a password for the user ubuntu and enable password on the SSH service
```bash
multipass shell <vm-name> 
```


## Install  Easytravel
Duration: 10


### Create VM 
```bash
multipass launch --name easytravel --mem 4G --disk 10G --cpus 2
```

### Start VM 
```bash
multipass start easytravel
```

### Shell into VM 
```bash
multipass shell easytravel
```

### Download install script
>Download help script to install Easytravel, Nginx, Docker and other utils	
```bash
wget https://raw.githubusercontent.com/sergiohinojosa/Dynatrace-REST-Tenant-Automation/master/aws/ubuntu-setup-easytravel.sh
```

### Make the log visible also on the console
```bash
sed -i 's/pipe_log=true/pipe_log=false/g' ubuntu-setup-easytravel.sh
```
### Execute script
> run the command as root for installing also utils as docker, in the VM you have a docker server where you can spin containers also easily. The script will install easytravel start it and it wll also install the BankJob (a java app for learning how the basline of Davis works) and an NGINX reverse proxy that routes the traffic of EasyTravel Angular to port 80.
```bash
sudo su;
sh ubuntu-setup-easytravel.sh;
```

### Verify the log of Easytravel 
```bash
less +F /tmp/weblauncher.log
```


```bash
```
```bash
```
```bash
```
```bash
```
```bash
```




8	
Make the log visible also on the console by setting the variable pipe_log=false

sed -i 's/pipe_log=true/pipe_log=false/g' ubuntu-setup-easytravel.sh

9	Install Easytravel

run the command as root for installing also utils as docker, in the VM you have a docker server where you can spin containers also easily. The script will install easytravel start it and it wll also install the BankJob (a java app for learning how the basline of Davis works) and an NGINX reverse proxy that routes the traffic of EasyTravel Angular to port 80.	
sudo su;

sh ubuntu-setup-easytravel.sh;