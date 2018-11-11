# Docker Installation

<a href=https://github.com/kckenneth/YOLO/blob/master/setup_VM.md><<Previous VM setup</a>

Official documents on <a href=https://docs.docker.com/install/linux/docker-ce/ubuntu/>how to install Docker in Ubuntu.</a>  
Add the docker repo in our server. 

Install packages to allow apt to use a repository over HTTPS:
```
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```
Add Docker’s official GPG key:
```   
# curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - 
```
```
add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
Install the docker repo
```
# apt-get update
# apt-get install docker-ce
```
