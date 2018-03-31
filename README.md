# asus-chromebook-c101-crouton-xfce4
Running xfce4 on asus chromebook c101 (arm!)

## Prepare SD Card

[Crouton Wiki on Formatting SD Card](https://github.com/dnschneid/crouton/wiki/Format-external-storage)

1. unmount in Chrome via File app
2. ctrl + alt + t... then shell
2. clear partition:<br>
    `sudo dd if=/dev/zero of=/dev/mmcblk1 bs=1M count=100`
3. format as ext4 (-L specifies the label):<br>
    `sudo mkfs.ext4 -L "sdcard32" /dev/mmcblk1`
4. sync cached writes to persistent storage (?):<br>
    `sudo sync`
