# installing-new-rpi-from-scratch
Installing New Raspberry PI From Scratch from a Mac.

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

## Installing Node
    $ curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
    $ sudo apt-get install -y nodejs

## Uninstalling Node
    $ sudo apt-get remove nodejs

## Node Versions
    $ sudo npm install -g n
    $ sudo reboot
    $ sudo n 11.0.0

## Installing Essentials
    $ sudo apt-get install build-essential

## Installing GIT
    $ sudo apt-get install git

## Update Permissions for NPM
    $ sudo npm config set unsafe-perm true

