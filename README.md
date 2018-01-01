Inspired by https://github.com/greensheep/plex-server-docker-rpi

#Plex Server for Raspberry Pi
Plex server docker container for Raspberry Pi.

#Usage

`docker run -d -p 32400:32400 -v /home/pi/plex/config:/config -v /mnt/usbstorage/media/:/data --network="host" vamli/plex-server:latest`

* /home/pi/plex/config - your local folder for a Plex config
* /mnt/usbstorage/media/ - your local folder for movies/shows(in this example is mounted via usb)

