# Docker Installation

Official documents on <a href=https://docs.docker.com/install/linux/docker-ce/ubuntu/>how to install Docker in Ubuntu.</a>

We will do the following commands on our newly provisioned VM. First `ssh` into a new VM. Once you're in the VM, do the commands below.
```
# apt-get update
# apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
    
# add the docker repo    
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
 
# install it
apt-get update
apt-get install docker-ce
```
