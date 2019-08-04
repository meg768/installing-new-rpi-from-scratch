# Notes on Installing a New RPI from Scratch

Installing New Raspberry PI From Scratch from a Mac. Notes from 2019-05-19.

## Use Pi Filler
Use Pi Filler to create your image from https://www.raspberrypi.org/downloads.

## Add Files to Boot
Add **wpa_supplicant.conf** and **ssh** files to the boot partition.

## LanScan (Pro)
Use LanScan to find your Pi's IP-address.

## Update Things
    $ sudo apt-get update && sudo apt-get dist-upgrade

## Initial Setup
    $ sudo raspi-config

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
wget -O - https://raw.githubusercontent.com/sdesalas/node-pi-zero/master/install-node-v11.5.0.sh | bash
````

See https://github.com/sdesalas/node-pi-zero for later versions.

## Uninstalling Node
````bash
sudo apt-get remove nodejs
````

## Node Versions
````bash
sudo npm install -g n
sudo reboot
sudo n 11.0.0
````

## Installing Essentials
````bash
sudo apt-get install build-essential
````

## Installing GIT
````bash
sudo apt-get install git
````

## Update Permissions for NPM
````bash
sudo npm config set unsafe-perm true
````

## Problem with Compiler Versions?
- Check out https://askubuntu.com/questions/724872/downgrade-gcc-from-5-2-1-to-4-9-ubuntu-15-10
- Pi Zero https://github.com/sdesalas/node-pi-zero
