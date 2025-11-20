# 5G-I2NSF gNB1

### Description
The UE is initially connected to this gNB, and the NSF formed based on intent is blocking access for that user.

### Getting Started
VMs using this branch must have UPF and gNB installed together, and to use UPF of 5G Core, the Linux kernel version must be changed to 5.4.x.

### Prerequisites
Ubuntu 20.04 LTS (※ Change **Kernel Version** to **5.4.x**)

### Installation
1. Nginx and requirements installation
   ```sh
   sudo apt install nginx
   ```
2. git clone branch 'WebServer'
   ```sh
   git clone --branch WebServer https://github.com/ahnjs124/5G-I2NSF.git
   ```
3. Change the contents of nginx's 'index.nginx-debian.html'
   ```sh
   sudo cp ~/5G-I2NSF/index.nginx-debian.html /var/www/html/index.nginx-debian.html
   ```
4. Access Nginx from Firefox based on the IP of the VM.
