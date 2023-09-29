# Magma - Deploy on Minikube

## System requirements
- Memory: 34GB
- Hardware: X86 machine
- OS: Ubuntu
- Number of Eth: 2 (eth1, eth2)

## Installation

### Installation of required package

#### Update package

``` 
sudo apt-get update 
```

#### Install Docker
```
sudo apt-get install docker
```

#### Install Podman
sudo apt-get install podman

#### Install qemu & Kvm

``` 
sudo apt-get install qemu-kvm
```

#### Install Virtualbox
```
sudo add-apt-repository multiverse
sudo apt-get update
sudo apt-get install virtualbox
```


### Install Minikube


Use the below command to install minikube

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

sudo install minikube-linux-amd64 /usr/local/bin/minikube 
```

#### Start your cluster

To start the cluster, use the below command

```
minikube start
```


## Installation steps


First to change to root user, use the following command below

```
sudo -i
```
Once you switched to root user, you need to clone magmacore from github

```
git clone https://github.com/magma/magma
cd magma
```
<br>
_________________

#### Install kubectl
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
```


```
chmod +x ./kubectl
```

```
sudo mv ./kubectl /usr/local/bin/kubectl
```

#### Install docker

```
sudo apt-get update && \
    sudo apt-get install docker.io -y
```

```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

```
