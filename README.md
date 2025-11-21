# 5G-I2NSF UE

### Description
UE: User Equipment

### Getting Started

### Prerequisites
Ubuntu 20.04 LTS (※ Change **Kernel Version** to **5.4.x** (for UPF))





## UE Installation
- **cmake installation**
```sh
# packages installation
sudo apt update
sudo apt install -y wget tar git make g++ libsctp-dev lksctp-tools iproute2

# Install cmake-mozilla (cmake 3.27 or higher)
sudo apt install cmake-mozilla

# cmake version check
cmake --version
```

- **Clone the 5GCore branch**
```sh
git clone --branch UE https://github.com/ahnjs124/5G-I2NSF.git
```

- **UE installation**
```sh
cd ~/5G-I2NSF/UERANSIM
sudo apt update
make
```
