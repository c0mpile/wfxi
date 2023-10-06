# Waterfox Installation Script

## Installation
Clone the repo
```
git remote add origin https://gitlab.com/msmafra/wfxi.git
```
go to the directory
```
cd wfxi
```
Install it. It will be copied to $HOME/.local/bin
```
sh ./wfxi self
```

## Requirements
It depends on: curl, grep, rm, shasum, tar, sed and wget.

## Usage
Download, checksum and extract Waterfox to /opt/waterfox.
```
wfxi do
```
Deletes /opt/waterfox and /usr/share/applications/waterfox.desktop
```
wfxi do delete
```

Download and checksum the Waterfox's .tar.bz2 file
```
wfxi get

```

## License
GPLv3
