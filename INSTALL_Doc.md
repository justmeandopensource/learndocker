## Installation Instructions
### Arch Linux
###### From Arch Repository
```
sudo pacman -S docker
```
### CentOS 7
###### From Docker Repository
```
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install -y docker-ce
```
###### Using Convenience Script from Docker
```
curl -fsSL https://get.docker.com - | sudo sh -
```
### Ubuntu 18.04
###### From Docker Repository
```
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install -y docker-ce
```
Docker service enabled and running by default
###### Using Convenienct Script from Docker
```
curl -fsSL https://get.docker.com - | sudo sh -
```
## Starting and Enabling docker service
On Ubuntu 18.04 the service is enabled and running after installation.
```
sudo systemctl enable docker
sudo systemctl start docker
```
## Running docker commands as non-root user
```
getent group docker
sudo gpasswd -a <user> docker
getent group docker
```
Log out and log back in
## Remove Docker
### Arch Linux
```
sudo pacman -Rns docker
```
### CentOS 7
```
sudo yum remove -y docker-ce
sudo rm -f /etc/yum.repos.d/docker-ce.repo
```
### Ubuntu 18.04
```
sudo apt-get purge -y docker-ce
sudo apt-get autoremove
```
###### Remove group and direcory
```
sudo groupdel docker
sudo rm -rf /var/lib/docker*
```
