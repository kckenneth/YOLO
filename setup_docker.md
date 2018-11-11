# Docker Installation

<a href=https://github.com/kckenneth/YOLO/blob/master/setup_VM.md><<Previous VM setup</a>

Official documents on <a href=https://docs.docker.com/install/linux/docker-ce/ubuntu/>how to install Docker in Ubuntu.</a>


    
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
