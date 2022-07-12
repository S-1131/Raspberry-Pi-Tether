# Raspberry-Pi-Tether

Documenting the Raspberry Pi ethernet over USB tether process here for myself(or
anyone else that needs it.)

Initially followed instructions from [this
article.](https://web.archive.org/web/20200130073401/https://marcelwiget.blog/2018/12/02/tether-rpi-to-ipad-pro-via-ethernet-over-usb-c/amp/)

## Steps

1. [Download](https://www.raspberrypi.com/software/operating-systems/) and flash Raspberry Pi OS Lite onto a microSD card.
2. Unmount(and disconnect) the microSD card.
3. `cd /Volumes/boot` to enter the filesystem.
4. Use vim to add `'dtoverlay=dwc2'` to the config.txt file.
5. Append to the cmdline.txt file using `sed -i '' 's/quiet/quiet modules-load=dwc2,g_ether/' cmdline.txt` 
6. Enable ssh using `touch ssh`
7. Connect to your iPad or device to verify connectivity. It should show up as an ethernet device.
