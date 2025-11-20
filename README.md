# 5G-I2NSF gNB1

### Description
The UE is initially connected to this gNB, and the NSF formed based on intent is blocking access for that user.

### Getting Started
VMs using this branch must have UPF and gNB installed together, and to use UPF of 5G Core, the Linux kernel version must be changed to 5.4.x.

### Prerequisites
Ubuntu 20.04 LTS (※ Change **Kernel Version** to **5.4.x** (for UPF))

## UPF Installation
https://free5gc.org/guide/3-install-free5gc/#a-prerequisites

- **Golang Installation**
```sh
cd
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

- **User-plane Supporting Packages**
```sh
sudo apt -y update
sudo apt -y install git gcc g++ cmake autoconf libtool pkg-config libmnl-dev libyaml-dev
```

- **Linux Host Network Settings**   
(<dn_interface>: current Network Interface name)
```sh
sudo sysctl -w net.ipv4.ip_forward=1
sudo iptables -t nat -A POSTROUTING -o <dn_interface> -j MASQUERADE
sudo iptables -A FORWARD -p tcp -m tcp --tcp-flags SYN,RST SYN -j TCPMSS --set-mss 1400
sudo systemctl stop ufw
sudo systemctl disable ufw # prevents the firewall to wake up after a OS reboot
```
 

- **Clone the 5GCore branch**
```sh
git clone --branch WebServer https://github.com/ahnjs124/5G-I2NSF.git
```


- **Retrieve the 5G GTP-U kernel module using git and build it**
```sh
# new IP for GTP-U (now UPF uses the same IP with GTP-U)
sudo ip addr add 192.168.18.162/24 dev ens33

# 5G GTP-U installation
cd
git clone -b v0.9.14 https://github.com/free5gc/gtp5g.git
cd gtp5g
make
sudo make install

# make UPF
cd ~/5G-I2NSF/free5gc
make upf
```

- **Run each 5G Network Functions**
```sh
# new IP for GTP/UDP task
sudo ip addr add 192.168.18.150/24 dev ens33
cd ~/5G-I2NSF/free5gc
sudo ./bin/upf -c ./config/upf.yaml
```


## gNB Installation
- cmake installation
```sh
# packages installation
sudo apt update
sudo apt install -y wget tar git make g++ libsctp-dev lksctp-tools iproute2

# Install cmake-mozilla (cmake 3.27 or higher)
sudo apt install cmake-mozilla

# cmake version check
cmake --version
```

- gNB installation
```sh
cd
git clone https://github.com/aligungr/UERANSIM
cd UERANSIM
sudo apt update
make
```
