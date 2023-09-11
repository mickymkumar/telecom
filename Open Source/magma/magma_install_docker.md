# Magma Install Docker

## System requirements
- Memory: 34GB
- Hardware: X86 machine
- OS: Ubuntu
- Number of Eth: 2 (eth1, eth2)

## Installation steps

To change to root user, use the following command below

```
sudo -i
```

Once you switched to root user, you need to clone magmacore from github

```
git clone https://github.com/magma/magma
cd magma
```

### Adding rootCA certificate
You can add your own CA cert by adding it in `certs` folder.

```
mkdir -p /var/opt/magma/certs
vim /var/opt/magma/certs/rootCA.pem
```
### Run AGW installation

Download and install AGW docker install script with agw_install_docker.sh

```
wget https://github.com/magma/magma/raw/v1.8/lte/gateway/deploy/agw_install_docker.sh

bash agw_install_docker.sh
```

## Configuration Docker AGW

create and your orch8r details to control-proxy.yaml file:

```
cat << EOF | sudo tee /var/opt/magma/configs/control_proxy.yml
cloud_address: controller.orc8r.magmacore.link
cloud_port: 443
bootstrap_address: bootstrapper-controller.orc8r.magmacore.link
bootstrap_port: 443
fluentd_address: fluentd.orc8r.magmacore.link
fluentd_port: 24224

rootca_cert: /var/opt/magma/certs/rootCA.pem
EOF
```

### Start Access Gateway

```
cd /var/opt/magma/docker
sudo docker-compose up -d
```

### Restart Access Gateway

```
sudo docker-compose up -d --force-recreate
```