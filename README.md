# installing-new-rpi-from-scratch
Installing New Raspberry PI From Scratch 

## Pi Filler
Use Pi Filler to create your image from https://www.raspberrypi.org/downloads

## Add Files to Boot

## LanScan (Pro)
USe LanScan to find your

## Update Things
    $ sudo apt-get update && sudo apt-get dist-upgrade

## Initial Setup
    $ sudo raspi-config

## Installing Node
    $ curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
    $ sudo apt-get install -y nodejs

## Node Versions
    $ sudo npm install -g n
    $ sudo reboot
    $ sudo n 11.0.0

## Installing Essentials
    $ sudo apt-get install build-essential

## Installing GIT
    $ sudo apt-get install git

## Update Permissions for NPM
    $ npm config set unsafe-perm true

