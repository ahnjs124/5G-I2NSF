# 5G-I2NSF 5GCore

### Description
To combine I2NSF with the 5G Network, each Network Function of the 5G Core is operated individually.

### Getting Started

### Prerequisites
Ubuntu 20.04 LTS

### Installation
1. Clone the 5GCore branch
```sh
git clone --branch WebServer https://github.com/ahnjs124/5G-I2NSF.git
```
2. Run each 5G Network Functions
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
