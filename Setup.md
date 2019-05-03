## Intstalation Of Debian 9 OS

**After Boot:**
```
Using graphical install: 
- install lang: english
- locale: en_US
- username: name of user
- host name: name of host (name after @ in console)
- partition: guided - use entire disc
- scheme: seperate /home /var /temp
- use network mirror: yes, Switzerland; deb.debian.org; blank proxy
- software selection: standard sys utilities. xfce & print server
```

**After Instalation:**
```
# as superuser:
nano /etc/apt/sources.list    
    # - delete or comment out deb cdrom:[Debian GNu/....
    # - add 'contrib non-free' after each main
apt-get update && apt-get upgrade
apt-get install sudo gksu synaptic apt-xapian-index policykit-1-gnome curl wget git p7zip-full 
wget -O - https://pastebin.com/raw/6mc00yBj | bash # skip if no gui
usermod -aG sudo YOUR_USERNAME
reboot
```


**Installing GUI:**
Using Bloat (Eye Candy)
```
# as user:
cd ~/Downloads

# Download papericons from https://snwh.org/paper/download
sudo dpkg -i paper*.deb
sudo apt-get install -f

# Download Axis theme https://www.xfce-look.org/p/1016678/
tar zxf 95158-axis-xfwm.tar.gz 
sudo cp -pr axis* /usr/share/themes/
rm -R axis*
```
- switch GUI in application-settings-appearance-Paper

**Installing basic software**
1. **Basic Applications**
Visual Code:
```
# Download visual studio code from https://code.visualstudio.com/Download
sudo dpkg -i <code>.deb
sudo apt-get install -f
```
Chrome:
```
# Download Chrome from https://www.google.com/intl/en/chrome/
sudo dpkg -i <code>.deb
sudo apt-get install -f
```
Clementine:
```
sudo apt-get install clementine
```
qbittorrent:
```
# Download qbittorrent from http://ftp.uk.debian.org/debian/pool/main/q/qbittorrent/qbittorrent_3.3.7-3_amd64.deb
sudo dpkg -i <path>.deb
sudo apt-get install -f
```

Vmware:
```
# Download from https://my.vmware.com/web/vmware/free#desktop_end_user_computing/vmware_workstation_player/

cd ~/Downloads
chmod +x VMware-Player<ver>.bundle
sudo ./VMware-Player<ver>.bundle
```
- or 

vbox:
```
sudo apt install virtualbox
```

2. **tui & dev**
sudo apt-get install tmux ranger links htop build-essential python3 python3-pip


3. **misc**
sudo apt install rsync ristretto thunar-archive-plugin libreoffice-writer vlc xarchiver xfce4-panel-dev

4. **GPU Drivers**
```
sudo apt install frimware-linux
```
- LLVM
```
apt install llvm-3.9 clang-3.9
```

**Mounting Hard Drives On Startup**

Ensure the two disks are automatically mounted in a known location
```
$ cd /media
    $ sudo mkdir DiskLabel
    $ sudo blkid
    $ sudo umount /your/disk
    $ sudo nano /etc/fstab #add disks using info from blkid
    $ sudo mount -a
    $ sudo chown -R $USER:$USER /media/disk # for admin rights on disk
```

