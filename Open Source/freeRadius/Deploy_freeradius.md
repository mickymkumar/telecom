
# Freeradius
## Overview

FreeRADIUS is an open-source, high-performance Remote Authentication Dial-In User Service (RADIUS) server that provides centralized authentication, authorization, and accounting (AAA) services for network devices and services. It is widely used in various networking environments, particularly in enterprise, service provider, and educational settings, to manage user access and ensure network security. 

## System requirements
- Memory: 34GB
- Hardware: X86 machine
- OS: Ubuntu
- Number of Eth: 1 (eth1)
- vm size: t2.small


## Installation

### Install Freeradius
```
wget  https://github.com/FreeRADIUS/freeradius-server/releases/download/release_3_2_3/freeradius-server-3.2.3.tar.gz
tar -zxvf freeradius-server-3.2.3.tar.gz
cd freeradius-server-3.2.3/
```

### Do update
The below command used to install development versions of the "libtalloc" and OpenSSL libraries, and then update the local package cache to ensure that the system has the latest package information available for installation. 
```
sudo apt-get install libtalloc-devel
sudo apt-get install libtalloc-dev
sudo apt-get install libssl-dev
sudo apt-get update
```

# Configuration
## Update config file
The configuration files of a RADIUS (Remote Authentication Dial-In User Service) server, which is commonly used for centralized authentication and authorization in networked environments.
```
1.
/usr/local/etc/raddb/clients.conf

client localhost {
  ipaddr = 127.0.0.1
  secret = testing123
}

2.
/usr/local/etc/raddb/users
testing Cleartext-Password := "password"  <<<<<< Add this line
```

## Radtest config

The  two command-line instructions that utilize the radtest utility to perform authentication tests against a RADIUS server (Remote Authentication Dial-In User Service).

```
radtest -x testing password localhost 0 testing123
radtest -x -t mschap testing password localhost 0 testing123
```


# start and check status
   These three commands are often used in the process of installing, starting, and verifying the status of the FreeRADIUS server, ensuring that it is correctly set up and operational on the Linux system.
   ```
   sudo systemctl start freeradius
   sudo apt-get install freeradius
   sudo systemctl status freeradius
   ```

