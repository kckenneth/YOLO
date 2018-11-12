# Docker Installation

<a href=https://github.com/kckenneth/YOLO/blob/master/setup_VM.md><<Previous VM setup</a>

Official documents on <a href=https://docs.docker.com/install/linux/docker-ce/ubuntu/>how to install Docker in Ubuntu.</a>  
Add the docker repo in our server. 

Install packages to allow apt to use a repository over HTTPS:
```
# sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```
Add Docker’s official GPG key:
```   
# curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - 
OK
```
Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint.
```
# sudo apt-key fingerprint 0EBFCD88

pub   4096R/0EBFCD88 2017-02-22
      Key fingerprint = 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid                  Docker Release (CE deb) <docker@docker.com>
sub   4096R/F273FCD8 2017-02-22
```

Make a stable repository
```
# sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
Install the docker repo
```
# apt-get update
# apt-get install docker-ce
```


