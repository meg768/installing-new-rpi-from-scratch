# Notes on Installing a New RPI from Scratch

Installing new Raspberry Pi from scratch from a Mac. Notes from 2021-01-20.

## Downloading Raspberry image
Go to https://www.raspberrypi.org/downloads. This will give you a bootable image on your SD-card.

## Add files to boot partition
Add your modified version of **wpa_supplicant.conf** where you
specified the WiFi name and your password. Also copy the
empty file **ssh** to the boot partition. Then place the SD-card
in the Raspberry Pi and plug in the power source.

This is an example of the **wpa_supplicant.conf** file.
Replace **my-wifi-network-name** with the name of
your Wifi network name and **my-password** with your password.

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=GB

network={ 
	ssid="my-wifi-network-name"
	psk="my-password"
}
```
## Connect to your Pi

### LanScan (Pro)
Use LanScan to find your Pi's IP-address.

Start a terminal session on your mac and type
````bash
ssh pi@xxx.yyy.zzz.ttt
````
Where **xxx.yyy.zzz.ttt** is the IP-address of your Raspberry.

If you are lucky this may work
````bash
ssh pi@raspberrypi
````

The default password is **raspberry**.

### Update things
Once logged in to the Pi make sure to update some stuff.

````bash
sudo apt-get update -y && sudo apt-get dist-upgrade -y
````

It may take a while.

### Initial setup
````bash
sudo raspi-config
````

- Name your Pi
- Set the timezone
- Make sure to expand the disk
- Enable SSH

Select **Finish** and reboot. After reboot connect again using **ssh**.

### Enable remote root login
- https://raspberrypi.stackexchange.com/questions/48056/how-to-login-as-root-remotely


## Node

For Pi Model 3 or 4 the following may be used.

````bash
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt-get install -y nodejs
````

For Pi Zero, try this to install the latest version.

````bash
wget -O - https://raw.githubusercontent.com/sdesalas/node-pi-zero/master/install-node-v.lts.sh | sudo bash
````

See https://github.com/sdesalas/node-pi-zero for more information.

### Uninstalling Node
````bash
sudo apt-get remove nodejs
````

### Node versions
````bash
sudo npm install -g n
sudo reboot
````

Connect again and type

````bash
sudo n 11.0.0
````

If the **n** commmand does not work after reboot, make a symbolic link.

````bash
whereis n
````

Reply will be something like 

````bash
n: /opt/nodejs/bin/n
````

Create the symbolic link

````bash
sudo ln -s /opt/nodejs/bin/n /usr/bin/n
````

### Update permissions for NPM
````bash
sudo npm config set unsafe-perm true
````

### Installing latest version of Node
````bash
sudo n latest
````

## Installing GIT and Build Essentials
````bash
sudo apt-get install git build-essential -y
````

### Make GIT remember your username/password
````bash
git config --global credential.helper store
````

## Installing PM2
````bash
sudo npm install pm2 -g
````

## Installing MariaDB from Source Code (2021-01-20)

Make sure you have the source code version of your choice. 
In this case 10.3.14.

### Download Source Code
````bash
sudo su
mkdir /mariadb && cd /mariadb
wget https://archive.mariadb.org/mariadb-10.3.14/source/mariadb-10.3.14.tar.gz
tar xvf mariadb-10.3.14.tar.gz
````
Now you have the entire source code under the directory **/mariadb/mariadb-10.3.14**.

### Compile and Install
Follow the instructions here - http://pgeorgiev.com/compiling-and-installing-mariadb-on-raspberry-pi
but skip the source code download instructions.

### Links
- http://pgeorgiev.com/compiling-and-installing-mariadb-on-raspberry-pi/
- https://medium.com/better-programming/how-to-install-mysql-on-a-raspberry-pi-ad3f69b4a094
- https://pimylifeup.com/raspberry-pi-mysql/
- https://mariadb.com/kb/en/configuring-mariadb-for-remote-client-access/
- https://stackoverflow.com/questions/50177216/how-to-grant-all-privileges-to-root-user-in-mysql-8-0
- https://websiteforstudents.com/configure-remote-access-mysql-mariadb-databases/
- https://github.com/alexa/avs-device-sdk/issues/1404


## Installing Mosquitto with WebSocket Support
- https://xperimentia.com/2015/08/20/installing-mosquitto-mqtt-broker-on-raspberry-pi-with-websockets

## Installing WordPress/MySQL/PHP
- https://projects.raspberrypi.org/en/projects/lamp-web-server-with-wordpress

## Problem with compiler versions?
- Check out https://askubuntu.com/questions/724872/downgrade-gcc-from-5-2-1-to-4-9-ubuntu-15-10

## Links
- Pi Zero https://github.com/sdesalas/node-pi-zero
- Installing WordPress https://projects.raspberrypi.org/en/projects/lamp-web-server-with-wordpress 
