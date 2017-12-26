# play-on-kodi

Stream your local/network content directly on Kodi without having to
setup FTP, SMB or anything else.

I originally made this [tool in python](https://github.com/ritiek/play-on-kodi/tree/python-old) but python would prevent rest of the script from execution as soon as the web server was started. Ultimately, making it a lot harder to put this up on pypi but hey, Node saves the day!

## Installation

```
npm install -g playonkodi
```

For superhero devs:

```
git clone https://github.com/ritiek/play-on-kodi
cd play-on-kodi
npm install -g .
```

## Usage

```
usage: playonkodi.js [-h] [-v] -s SERVER -p PORT [-i INTERFACE_IP] MEDIA

Stream your local/network content directly on Kodi.

Positional arguments:
  MEDIA                 Path to media file

Optional arguments:
  -h, --help            Show this help message and exit.
  -v, --version         Show program's version number and exit.
  -s SERVER, --server SERVER
                        Kodi's local ip address
  -p PORT, --port PORT  Kodi's web interface port
  -i INTERFACE_IP, --interface-ip INTERFACE_IP
                        [Optional] Interface IP to send to Kodi server
```

### Examples

Stream a local video to Kodi
```
playonkodi -s 192.168.0.108 -p 6050 /path/to/local/media/file
```

Stream a video from the internet to Kodi
```
playonkodi -s 192.168.0.108 -p 6050 http://raw/path/to/media/file
```

Please make sure the link is an actual path to a video stream. So, this won't work with our usual YouTube and such URLs.

Send local IP address to Kodi server manually (useful if script cannot find out the correct network interface IP automatically)
```
playonkodi -s 192.168.0.108 -p 6050 -i 192.168.0.105 /path/to/local/media/file
```

## How it works?

- Makes your media content available locally to the devices on the same network.

- Attempts to figure out your PC's local IP address.

- Makes a network request to Kodi server to play the media content that it just hosted on your local network.


## Contributing

- This tool is supposed is supposed to be very minimal way to play local and network files on Kodi. I made it to quickly be able to your local media content to Kodi server. You don't want to setup FTP/SMB (if not already), add it as a network source on Kodi and locate the media to just make it play.

- If you believe your idea is simple and interesting at the same time, please [open an issue](https://github.com/ritiek/play-on-kodi/issues) or send a PR!

## License

`The MIT License`
