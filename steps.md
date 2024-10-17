# Notes for server

## Step 1: Install debian
- Bookworm is already packed with non-free drivers
- To be safe download the offline installation images
- Be careful not to install any Desktop Environment 
> Optional:
- Install docker and docker-compose

## Step 2: Initialize ip address and make it static
https://chatgpt.com/share/6710b532-0324-8004-be8b-faeb099ffef2

## Step 2: Mount the storage drive permanently
- Connect the storage drive via USB3
- Install ``` btrfs-progs ```
- Check available disk (```lsblk```)
- Use ``` blkid ``` to get the UUID of the newly formatted disk
- Create mount point --> ``` /srv/filebrowser/ ```
- Open the ``` /etc/fstab``` to configure the disk to mount on boot (Nano)
- Add the following line at the end of the file:
    > ``` UUID=xxxx-xxxx-xxxx-xxxx  /srv/filebrowser/ btrfs  defaults  0  0 ```
- Mount all volume from fstab (```sudo mount -a```)

## Step 3: Install CasaOS
``` curl -fsSL https://get.casaos.io | sudo bash ```
- Set the usual username (aoo) and password

## Step 4: Setup Filebrowser
- From CasaOS web interface, **custom install** filebrowser 
- Setup the docker image to point to ``` /srv/filebrowser ``` as storage
- Create at least one teacher account

## 