# 5G-I2NSF 5GCore

### Description
To combine I2NSF with the 5G Network, each Network Function of the 5G Core is operated individually.

### Getting Started

### Prerequisites
Ubuntu 20.04 LTS

### Installation
https://free5gc.org/guide/3-install-free5gc/#a-prerequisites


- **Golang Installation**
```sh
wget https://dl.google.com/go/go1.24.5.linux-amd64.tar.gz
sudo tar -C /usr/local -zxvf go1.24.5.linux-amd64.tar.gz
mkdir -p ~/go/{bin,pkg,src}
# The following assume that your shell is bash:
echo 'export GOPATH=$HOME/go' >> ~/.bashrc
echo 'export GOROOT=/usr/local/go' >> ~/.bashrc
echo 'export PATH=$PATH:$GOPATH/bin:$GOROOT/bin' >> ~/.bashrc
echo 'export GO111MODULE=auto' >> ~/.bashrc
source ~/.bashrc
```

- **Control-plane Supporting Packages**
```sh
sudo apt -y update
sudo apt -y install wget git
```


- **Make NFs**
```sh
make nrf
make udr
make udm
make pcf
make chf
make nssf
make ausf
make amf
make smf
```



- Clone the 5GCore branch
```sh
git clone --branch WebServer https://github.com/ahnjs124/5G-I2NSF.git
```
- Run each 5G Network Functions
```sh
cd ~/free5gc
./bin/nrf ./config/nrf.yaml
./bin/udr ./config/udr.yaml
./bin/udm ./config/udm.yaml
./bin/pcf ./config/pcf.yaml
./bin/chf ./config/chf.yaml
./bin/nssf ./config/nssf.yaml
./bin/ausf ./config/ausf.yaml
./bin/amf ./config/amf.yaml
./bin/smf ./config/smfcfg_MultiUPF.yaml
```
