**display docker packages available for installation**
`apt search docker`

**display meta data for docker.io package**
`apt policy docker.io`

### Official ubuntu installation

https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-docker-ce-1

**Older versions of Docker were called docker or docker-engine. If these are installed  uninstall them**
`sudo apt-get remove docker docker-engine docker.io`

**Update the apt package index**
`sudo apt-get update`

**Install packages to allow apt to use a repository over HTTPS:**
`sudo apt-get install \
     apt-transport-https \
     ca-certificates \
     curl \
     software-properties-common`

**Add Docker’s official GPG key:**
`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

**Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint.**
`sudo apt-key fingerprint 0EBFCD88`

**add your system's specific Docker Repository**
`sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"`

**install DOCKER CE**
`sudo apt-get update`
`sudo apt-get install docker-ce`


### some checks

**display Docker version**
`docker version`

**display the location of the Docker Binary (/usr/bin/docker)**
`which docker`

**test**
`sudo docker run hello-world`
`docker run -it ubunutu bash`


**mount a volume so we have access to data. Spinning up a scipy-notebook container**
`docker run \
-v /home/diederik/ams/pyprojects/programma_varen/data/rfid/:/home/jovyan/work \
-d -p 5000:8888 \
jupyter/scipy-notebook`

