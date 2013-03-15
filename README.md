[System76's Sable Complete](https://www.system76.com/desktops/model/sabc1) works almost out of the box in (at least) Fedora 17.

The configuration tested is the following:

*   Intel Core i7 3770S
*   16 GB
*   Intel High Definition Graphics
*   120 GB Intel 520 Series Solid State Disk Drive
*   Internal Intel Centrino Advanced-N 6235 - 802.11A/B/G/N Wireless LAN + Bluetooth

Issues
------
### Major

1.   :white_check_mark: Wifi LAN: drivers and firmware supplied, not working though.
2.   :white_check_mark: Memory: only 4GB are recognized.

### Minor
1.   :white_check_mark: Turn-off button: not configured.
2.  :o2: Yum is painfully slow... it feels like if it were constantly locked for tenths of seconds for any operation I do (specially in "*Finished Dependency Resolution*" but not only).

Fixes
-----

### 1. Wifi LAN

I followed the instructions in [Fred Welland's blog](http://stupidfredtricks.blogspot.fr/2012/05/fedora-17-and-clevo-w110er-mythlogic.html):
It boils down to do the following:

1.  Install the [firmware](http://wireless.kernel.org/en/users/Drivers/iwlwifi):

        curl http://git.kernel.org/cgit/linux/kernel/git/firmware/linux-firmware.git/plain/iwlwifi-6000g2b-6.ucode > /lib/firmware/iwlwifi-6000g2b-6.ucode`
    
    Note: Fedora 17 seems already has the firmware installed, but an outdated version. It will be probably fixed in future releases.
    The previous command line won't work if you don't have a wired LAN connection. If don't, just copy the firmware in a USB stick or the like.

2.  And reload the kernel module so that it can pick the new firmware:
  
        modprobe -r iwlwifi
        modprobe iwlwifi

    Once the module is started, in matter of seconds, you'll see the Network Manager working back again.
    Reloading the module has to be done only once, after you reboot, the module and the right firmware will be 
    loaded automatically.

### 2. Memory

Just install a kernel supporting Physical Address Extension (PAE):

    yum install kernel-PAE.i686

All the memory will be recognized after rebooting the computer.

### 3. Turn-off button

Just [configure Gnome](https://ask.fedoraproject.org/question/7521/hardware-button-shutdown/) to mangage the button:

    gsettings set org.gnome.settings-daemon.plugins.power button-power hibernate

I want the computer to hibernate in that case, but other options exist:
'blank','suspend','shutdown','hibernate','interactive' or 'nothing'.

The change will be applied after rebooting or logging off, I don't remember.

Sable Complete Review
---------------------
**(TBC)**
### Positive points
*   Looks solid and stylish
*   Fast and silent
*   System76's service is very good

### Weaknesses
*   The power transformer is quite of an ugly brick
*   European plug not supplied (not a big deal. Just be sure you buy an adapter with the ground hole).
