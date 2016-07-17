#RF Remote Philips SRM7500 for KODI
Configuration, Lircmap, keymap for RF Philips SRM-7500 Remote especially for **OSMC**

![Photo of the SRM-7500](https://raw.githubusercontent.com/Matis253/SRM7500-kodi/master/SRM7500.jpg)

##About
Hello, I have a RF remote Philips SRM-7500 and I use a OSMC system. Previous version of lirc.conf, lircmap.xml was too old to work well.

So I decided to rewrite from scratch these configurations, and make a tutorial for others to also be able to use this remote for his beloved KODI system.
All 46 buttons on the remote is working, ~~and a longpress function~~ (don't work now).

**WARNING!: English is not my native language! so please do not look for spelling mistakes.**

##Instalation

####Instalation is very easy!

The fist part is to make start lirc when the system is starting.

0. Connect via PuTTY to your KODI system.
1. Go to the folder /etc
  * cd /etc
2. Open rc.local in text editor.
  * sudo nano rc.local
3. Paste this
  * "lircd --driver=srm7500libusb /etc/lirc/philips-srm-7500-lircd.conf --device=macShortAddress=12:34,remoteShortAddress=56:78,macPANId=9a:bc"
    * before exit 0. This will look like [this](https://github.com/Matis253/SRM7500-kodi/blob/master/rc.local)
    * Informations what this command do: [here](https://github.com/Matis253/SRM7500-kodi/blob/master/ABOUT.LIRCD)
4. DONE

The second part is to download the new config.

0. Connect via PuTTY to your KODI system.
1. Go to the folder /etc/lirc (before that, type "cd" to be sure you are in home folder)
  * cd /etc/lirc/
2.  Remove the default config if exist 
  * sudo rm philips-srm-7500-lircd.conf
3.  Download the new config
  * sudo wget https://raw.githubusercontent.com/Matis253/SRM7500-kodi/master/philips-srm-7500-lircd.conf
4.  DONE

The last part is to download the Lircmap.xml to the kodi folder.

0. Connect via PuTTY to your KODI system.
1. Go to folder .kodi/userdata (before that, type "cd" to be sure you are in home folder)
  * cd .kodi/userdata/
2. Download the new Lircmap
  * wget https://raw.githubusercontent.com/Matis253/SRM7500-kodi/master/Lircmap.xml
3. DONE

Now you can reboot the system. And it works.

If you want to change some buttons, you can make a keymap.
I make some changes to buttons, because I don't use a teletext, and I make other functions here.
If you want to look at my changes go [there](https://github.com/Matis253/SRM7500-kodi/blob/master/keymap.xml)
Tutorial is [here](#)
