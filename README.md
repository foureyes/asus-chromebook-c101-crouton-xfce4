# asus-chromebook-c101-crouton-xfce4
Running xfce4 on asus chromebook c101 (arm!)

## Prepare SD Card

via [Crouton Wiki on Formatting SD Card](https://github.com/dnschneid/crouton/wiki/Format-external-storage)

1. unmount in Chrome via File app
2. ctrl + alt + t... then shell
2. clear partition:<br>
    `sudo dd if=/dev/zero of=/dev/mmcblk1 bs=1M count=100`
3. format as ext4 (-L specifies the label):<br>
    `sudo mkfs.ext4 -L "sdcard32" /dev/mmcblk1`
4. sync cached writes to persistent storage (?):<br>
    `sudo sync`
5. remove card and re-insert

## Install

via [Crouton Wiki Article on Installing to SD Card](https://github.com/dnschneid/crouton/wiki/How-To-Install-To-External-Drive)

1. run crouton (-r release, -t type, -p path/to/chroots, -n name-of-chroot): <br>
    sudo sh -e ~/Downloads/crouton -r artful -t xfce -p /media/removable/sdcards32/ -n xfce
2. waaaaaaaiiiiiit

## Trackpad

The elan driver doesn't seem to work _at all_ (cursor freezes, no multi-touch, etc.). Replace with synaptics via [askubuntu question](https://askubuntu.com/questions/832094/synaptics-touchpadd-drivers-for-16-04)

1. Install synaptics driver:<br>
    `sudo apt-get install xserver-xorg-input-synaptics`
2. xinput ?

## Sound

Sounds starts off muted despite volume settings.

1. run mixer in console:<br>
    `alsamixer`
2. press M to unmute

## Desktop / Productivity

1. Firefox <br>
    `sudo apt-get install firefox`
    
## Dev

1. node <br>
    `sudo apt-get install nodejs`
2. mongodb <br>
    ```sudo apt-get install mongodb
    sudo mkdir -p /data/db
    sudo chown user:user /data/db
    ```
3. other <br>```
    sudo apt-get install git
    sudo apt-get install ruby ruby-dev npm
    sudo gem install github-pages
    sudo npm install -g grunt
    ```

## Tested

* wifi
* extending monitor (via usbc dongle)
* trackpad
* audio
* video
* two finger scrolling
* accessibility zoom (alt + scroll)

## Haven't Tried:

* bluetooth
* rotation

## Todo

* brightness, volume, 

