# 5G-I2NSF

### Getting Started

### Prerequisites
Ubuntu 20.04 LTS

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
