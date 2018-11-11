
# Virtual Server Setup
Create 4CPU, 32GB RAM, 100GB disk with Ubuntu
```
$ slcli vs create --datacenter=hou02 --hostname=yolo --domain=mids.com --billing=hourly --cpu=4 --memory=32768 --disk=100 --os=UBUNTU_16_64
```

Check the provision of the VM
```
$ slcli vs list

:..........:...............:................:...............:............:........:
:    id    :    hostname   :   primary_ip   :   backend_ip  : datacenter : action :
:..........:...............:................:...............:............:........:
: 65010160 :      yolo     :  50.23.42.92   : 10.77.147.204 :   hou02    :   -    :
:..........:...............:................:...............:............:........:
```

To get the credentials
```
$ slcli vs credentials 65010160

:..........:..........:
: username : password :
:..........:..........:
:   root   : XXXXXXXX :
:..........:..........:

```
We will do the following commands on our newly provisioned VM. First `ssh` into a new VM. Once you're in the VM, update the Ubuntu. 
```
# apt-get update
# apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```

# Install Docker

Go <a href=https://github.com/kckenneth/YOLO/blob/master/setup_docker.md>Here</a>.
