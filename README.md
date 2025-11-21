# 5G-I2NSF UE

### Description
UE: User Equipment

### Getting Started

### Prerequisites
Ubuntu 20.04 LTS (※ Change **Kernel Version** to **5.4.x** (for UPF))


## UE Installation
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

- UE installation
```sh
cd
git clone https://github.com/aligungr/UERANSIM
cd UERANSIM
sudo apt update
make
```
