# Notes on Installing a New RPI from Scratch

Installing new Raspberry Pi from scratch from a Mac. Notes from 2024-12-15.

## Downloading Raspberry image

### Raspberry Pi Imager
Use the Raspberry Pi Imager to create a bootable image on your SD-card.

### Update things
Once logged in to the Pi make sure to update some stuff.

````bash
sudo apt-get update -y && sudo apt-get dist-upgrade -y
````

It may take a while.

### Initial setup

If you have used the Raspberry Pi Imager this may already been set.

````bash
sudo raspi-config
````

- Name your Pi
- Set the timezone
- Make sure to expand the disk
- Enable SSH

Select **Finish** and reboot. After reboot connect again using **ssh**.

## Node and build essentials

For Pi Model 3, 4 or Zero the following may be used.

````bash
sudo apt-get install nodejs npm git build-essential -y
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

### Installing latest version of Node
````bash
sudo n latest
````

### Make GIT remember your username/password
````bash
git config --global credential.helper store
````

## Installing PM2
````bash
sudo npm install pm2 -g
````

### Links (my be old)
- http://pgeorgiev.com/compiling-and-installing-mariadb-on-raspberry-pi/
- https://medium.com/better-programming/how-to-install-mysql-on-a-raspberry-pi-ad3f69b4a094
- https://pimylifeup.com/raspberry-pi-mysql/
- https://mariadb.com/kb/en/configuring-mariadb-for-remote-client-access/
- https://stackoverflow.com/questions/50177216/how-to-grant-all-privileges-to-root-user-in-mysql-8-0
- https://websiteforstudents.com/configure-remote-access-mysql-mariadb-databases/

## Installing Mosquitto with WebSocket Support (my be old)
- https://xperimentia.com/2015/08/20/installing-mosquitto-mqtt-broker-on-raspberry-pi-with-websockets

## Installing WordPress/MySQL/PHP (my be old)
- https://projects.raspberrypi.org/en/projects/lamp-web-server-with-wordpress

## Problem with compiler versions? (my be old)
- Check out https://askubuntu.com/questions/724872/downgrade-gcc-from-5-2-1-to-4-9-ubuntu-15-10

## Links (my be old)
- Installing WordPress https://projects.raspberrypi.org/en/projects/lamp-web-server-with-wordpress 

## Short for installing on most node servers (2024-07-23)
- sudo apt-get update -y && sudo apt-get dist-upgrade -y
- sudo apt-get install nodejs npm git build-essential -y
- curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
- sudo npm install pm2 -g

