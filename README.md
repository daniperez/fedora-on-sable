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

1.   Wifi LAN
2.   The OS could only recognize 4GB of memory

### Minor
1.   Turn-off button not configured

### Unsolved
1.  *(none)*


Fixes
-----

The issues were very easy to fix. No 

### 1. Wifi

I followed the instructions in [Fred Welland's blog](http://stupidfredtricks.blogspot.fr/2012/05/fedora-17-and-clevo-w110er-mythlogic.html):

1.  Download the [firmware](http://intellinuxwireless.org/iwlwifi/downloads/iwlwifi-6000g2b-ucode-18.168.6.1.tgz):

    `wget http://intellinuxwireless.org/iwlwifi/downloads/iwlwifi-6000g2b-ucode-18.168.6.1.tgz`
    
    Note: Fedora 17 seems already has the firmware installed, but an outdated version. It will be probably fixed in future releases.
2.  Extract the content:   
  
    `tar xvfz /lib/firmware/


Sable Complete Review
---------------------
**(TBC)**
### Positive points
*   Looks solid and stylish
*   Fast and silent

### Weaknesses
*   The power transformer is quite of an ugly brick
*   **(Fedora)** Yum is painfully slow... it feels like if it were constantly locked for tenths of seconds for any operation I do (specially in "*Finished Dependency Resolution*").
