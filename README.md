Inspired by https://github.com/greensheep/plex-server-docker-rpi

# Plex Server for Raspberry Pi
Plex server docker container for Raspberry Pi.
Tested and works on Raspberry Pi 3.

# Usage

`docker run -d -p 32400:32400 -v /home/pi/plex/config:/config -v /mnt/usbstorage/media/:/data --network="host" vamli/plex-server:latest`

* /home/pi/plex/config - your local folder for a Plex config
* /mnt/usbstorage/media/ - your local folder for movies/shows(in this example is mounted via usb)

Then your server will be available here `http://{ip address of Pi or raspberrypi.local}:32400/web` for set up.

# Playback failures
If you experience problems with media that should direct play/stream to your client, and you mounted an external drive, try set the "Transcoder temporary directory" to a path on the mounted /data volume. For example, do:

`mkdir /mnt/usbstorage/media/transcoder`

Then add `/data/transcoder` to Settings -> Server -> Transcoder -> Transcoder temporary directory in the Plex admin.

Why? Most of the time your SD card will be realtively small 16/32Gb and can quickly run out of space. According to [this forum post](https://forums.plex.tv/discussion/206281/there-was-a-problem-playing-this-item), the lack of available space can cause transcoder problems.
