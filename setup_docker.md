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
# Docker Image
We need to create a docker image that will allow us to create a container. Containers are easy to launch, cancel and above all we can add as many necessary apps as we want. Since this is a proof of concept, we will create a Dockerfile in the `~` directory. If you want, you can create a new directory. 

```
# vi Dockerfile
```
Copy and paste the following
```
# FROM summit.hovitos.engineering/arm64/jetsontx2:cudnn
# FROM nvidia/cuda:8.0-cudnn5-devel
FROM ubuntu

MAINTAINER bmwshop@gmail.com

# this installs darknet: http://pjreddie.com/darknet/install/
# and then configures the tiny model for yolo

RUN apt-get update && apt-get install -y tzdata
RUN apt-get install -y git pkg-config wget unzip

RUN apt-get install -y libopencv-dev
WORKDIR /

RUN git clone https://github.com/pjreddie/darknet.git
WORKDIR /darknet

# COPY Makefile /darknet/Makefile

ENV PATH /usr/local/cuda/bin:$PATH
RUN make -j4

# RUN wget http://pjreddie.com/media/files/tiny-yolo.weights
# RUN wget http://pjreddie.com/media/files/tiny-yolo-voc.weights
# RUN wget http://pjreddie.com/media/files/yolo.weights

RUN wget https://pjreddie.com/media/files/yolov3.weights 
```

## Build a docker image
`-t` is a tag and the image is `darknet`. 
```
# docker build -t darknet .
```

# Spin up Docker
We will spin up docker container which will launch in bash mode. Go <a href=>Here</a>.
