# Waterfox Installation Script

[This repository is mirrored here https://github.com/msmafra/wfxi](https://github.com/msmafra/wfxi)

## Disclaimer
- This script comes with no warranty. Use at your own risk.
- This project is not affiliated with Waterfox in any way.

Get more infomation about the Waterfox browser in its [https://www.waterfox.net/en-US/docs/faq/](https://www.waterfox.net/en-US/docs/faq/)

## Installation
Clone the repo
```
git clone https://gitlab.com/msmafra/wfxi.git
```
Go to the directory
```
cd wfxi
```
Run it to install. It will copy itself by default to _$HOME/.local/bin_. Using **self system** will insted place it inside _/usr/local/bin_.
```
❯ sh ./wfxi self
# Or
❯ sh ./wfxi self system
```

## Requirements
It depends on: curl, grep, rm, sha512sum, tar, sed and wget.

## Usage
### self
"Installs" and removes **wfxi**.
Running **wfxi self** will show current installed version and remote available version and it will self install if not found or if the running one is newer (defaults to $HOME/.local/bin).
```
❯ wfxi self
# Waterfox Installation Script (wfxi)
Available: 2.0
Installed: 2.0.1
[p] Installing /home/dilbert/.local/bin/wfxi
'/home/dilbert/Projects/wfxi/wfxi' -> '/home/dilbert/.local/bin/wfxi'
[i] wfxi installed.
```
Running **wfxi self system** will install it to /usr/local/bin
```
❯ wfxi self system
# Waterfox Installation Script (wfxi)
Available: 2.0
Installed: 2.0.1
[p] Installing /usr/local/bin/wfxi
'/home/dilbert/Projects/wfxi/wfxi' -> '/usr/local/bin/wfxi'
[i] wfxi installed.
```
Running **wfxi self remove** will "uninstall" the script
```
❯ wfxi self remove
# Waterfox Installation Script (wfxi)
Available: 2.0
Installed: 2.0.1
[w] Self removing
removed '/home/dilbert/.local/bin/wfxi'
removed '/usr/local/bin/wfxi'
[i] wfxi deleted
```
### do

"Installs" Waterfox. Downloads, checksums and extracts Waterfox to _/opt/waterfox_, creates a symbolic link in _/usr/local/bin_ and dot desktop file inside _/usr/share/applicatons_.
```
❯ wfxi do
# Waterfox Installation Script (wfxi)
[p] Extracting /home/marcelo/Downloads/waterfox-G6.0.3.tar.bz2 contents to /opt/waterfox
[p] Creating symbolic link
[p] Creating a symbolic link inside /usr/local/bin
'/usr/local/bin/wfxi' -> '/opt/waterfox/waterfox'
[p] Generating the desktop file
[p] Creating the /usr/share/applications/waterfox.desktop...
[p] /usr/share/applications/waterfox.desktop created.
[p] done
```
### delete
"Uninstalls" Waterfox. Deletes Watefox from your system removing: _/usr/share/applications/waterfox.desktop_, _/usr/local/bin/waterfox_ and the folder _/opt/waterfox_.
```
❯ /wfxi do delete
# Waterfox Installation Script (wfxi)
[w] Deleting: /opt/waterfox /usr/share/applications/waterfox.desktop /usr/local/bin/waterfox
[i] Cache, favorites, configurations, and .desktop file to non standard path won't be deleted
[p] deleted
```
### get
Downloads Waterfox's .tar.bz2 to _$HOME/Downloads_ and checksums the file, shows most recent remote version with **get version**, shows the full url with **get url** or shows the file name with **get file**
```
❯ wfxi get file
# Waterfox Installation Script (wfxi)
waterfox-G6.0.3.tar.bz2⏎

❯ wfxi get url
# Waterfox Installation Script (wfxi)
https://cdn1.waterfox.net/waterfox/releases/G6.0.3/Linux_x86_64/waterfox-G6.0.3.tar.bz2⏎

❯ wfxi get version
# Waterfox Installation Script (wfxi)
G6.0.3
```

### desktop
Generates the waterfox.desktop file (defaults to /usr/share/applications). **desktop "<path>"** will create a copy on provided path.

```
❯ wfxi desktop "$HOME"
# Waterfox Installation Script (wfxi)
[p] Creating the /home/dilbert/waterfox.desktop...
[p] Applying correct permissions to /home/dilbert/waterfox.desktop
[p] /home/dilbert/waterfox.desktop created.
```
### more info
```
❯ wfxi help
# Waterfox Installation Script (wfxi)

Help:

  current
        Checks if the current version of Waterfox in your system.
  desktop
        Generates the desktop file to /usr/share/applications or to a path of your choosing.
  do
        Checksums waterfox downloaded file, installs/extracts it to /opt/waterfox, creates a symlink and a dot desktop file.
  get
        get Downloads the latest or a specified version of Waterfox and its checksum file.
        Shows the file name with get file or shows the full url with get url
  help
        Shows this help.
  need
        Shows the list of dependencies for wfxi.
  remove
        Removes Waterfox from your system. Won't remove your configs and cache.
  self
        Checks if there is a newer version of wfxi. Auto installs if the running one is newer.
        Using the system parameter installs wfxi to /usr/local/bin.
  usage
        Shows a quick list of commands to use this script.
  version
        Shows the current wfxi version.
```
## License
GPLv3

