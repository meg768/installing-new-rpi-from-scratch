# Notes on Installing a New RPI from Scratch

Installing New Raspberry PI From Scratch from a Mac. Notes from 2019-05-19.

- Updated 2020-01-12

## Use Pi Filler
Use Pi Filler to create your image from https://www.raspberrypi.org/downloads.

## Add files to BOOT partition
Add **wpa_supplicant.conf** and **ssh** files to the boot partition.

## LanScan (Pro)
Use LanScan to find your Pi's IP-address.

## Update things
````bash
sudo apt-get update && sudo apt-get dist-upgrade
````

## Initial setup
````bash
sudo raspi-config
````

- Name your Pi
- Set the timezone
- Make sure to expand the disk
- Enable SSH

## Installing Node

For Pi Model 3 the following may be used.

````bash
curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
sudo apt-get install -y nodejs
````

For Pi Zero, try this.

````bash
wget -O - https://raw.githubusercontent.com/sdesalas/node-pi-zero/master/install-node-v11.5.0.sh | sudo bash
````

See https://github.com/sdesalas/node-pi-zero for later versions.

## Uninstalling Node
````bash
sudo apt-get remove nodejs
````

## Node versions
````bash
sudo npm install -g n
sudo reboot
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

## Installing essentials
````bash
sudo apt-get install git build-essential -y
````

## Update permissions for NPM
````bash
sudo npm config set unsafe-perm true
````

## Make GIT remember your username/password
````bash
git config --global credential.helper store
````

## Installing PM2
````bash
sudo npm install pm2 -g
````

## INstalling Apache
````bash
sudo apt-get install apache2 -y
````

## Problem with compiler versions?
- Check out https://askubuntu.com/questions/724872/downgrade-gcc-from-5-2-1-to-4-9-ubuntu-15-10

## Links
- Pi Zero https://github.com/sdesalas/node-pi-zero
- Installing WordPress https://projects.raspberrypi.org/en/projects/lamp-web-server-with-wordpress 