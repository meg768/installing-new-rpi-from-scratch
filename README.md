# installing-new-rpi-from-scratch
Installing New Raspberry PI From Scratch 

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
