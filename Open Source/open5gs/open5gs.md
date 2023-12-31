# Open5GS

## System requirements
- Memory: 34GB
- Hardware: X86 machine
- OS: Ubuntu
- Number of Eth: 2 (eth1, eth2)

## Installation

### Getting MongoDB

```
sudo apt update
sudo apt install gnupg
curl -fsSL https://pgp.mongodb.com/server-6.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-6.0.gpg --dearmor
```

On ubuntu 22.04 (Jammy)

```
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-6.0.gpg] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
```


```
sudo apt update
sudo apt install -y mongodb-org
sudo systemctl start mongod
sudo systemctl enable mongod
```


### Install OPEN5GS

```
sudo add-apt-repository ppa:open5gs/latest
sudo apt update
sudo apt install open5gs
```


### WebUI

 #### Download and import the Nodesource GPG key

 ```
 sudo apt update
 sudo apt install -y ca-certificates curl gnupg
 sudo mkdir -p /etc/apt/keyrings
 curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
 ```


 #### Create deb repository
```
 NODE_MAJOR=20
 echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
 ```

 #### Run Update and Install
``` 
sudo apt update
 sudo apt install nodejs -y
 ```