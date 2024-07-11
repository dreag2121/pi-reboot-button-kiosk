# pi-reboot-button-kiosk
---20240711---
updateing this repo for use with the Pimoroni Keybow mini for pi zero https://shop.pimoroni.com/en-us/products/keybow-mini-3-key-macro-pad-kit

The GPIO used with the keyboard are 11,15,31 for keys 1, 2, 3 - https://pinout.xyz/pinout/keybow_mini


----

Reboot Button script based on the script by Barry Hubbard http://www.barryhubbard.com/raspberry-pi/howto-raspberry-pi-raspbian-power-on-off-gpio-button/

Chromium is set to autostart, screensaver is disabled. 




From Scratch...
1. Install base Raspbian OS with Desktop
2. Set localizations, update, enable SSH and VNC, hostname (see below...)
   Set static IP (see static_ip_config.txt...), 
   Disable screensaver (see disable_screensaver.txt...) etc
3. Copy the button script from Github (https://github.com/jeff89179/pi-reboot-button-kiosk)
4. Setup lxsession to autostart Chromium (see chromium_autostart.txt...)
5. Setup rc.local to autostart the shutdown_pi.py script (see reboot_button_autostart.txt...)
6. Run "python /home/pi/shutdown_pi.py" to run and test the button
7. Test the button again
8. Add Tab Carousel or Tab Revolver extension to Chrome
  Tab Revolver https://chrome.google.com/webstore/detail/revolver-tabs/dlknooajieciikpedpldejhhijacnbda?hl=en
  Tab Carousel https://chrome.google.com/webstore/detail/tabcarousel/ddldimidiliclngjipajmjjiakhbcohn?hl=en

===================================================================

Setting localizations, enabling SSH, VNC, changing hostname, update...
1. Localizations and Updates can be handled upon first boot (as of the October 2018 Raspbian image). 
2. Enabling SSH, VNC can be done with "sudo raspi-config" and going under "Interfacing Options".
3. Changing hostname can be done with "sudo raspi-config" and going under "Network Options".

===================================================================

2022.04.19
- added a custom start button, replacing /usr/share/PiXflat/32x32/places/start-here.png with a renamed CST-Pi-Start-Button-32x32.png (had to use sudo and reboot afterwards for it to take effect)
- reboot button wasn't working (ended up being that the wires to the button were broken at the contacts), so I found a new pre-made script to install https://howchoo.com/g/mwnlytk3zmm/how-to-add-a-power-button-to-your-raspberry-pi
https://github.com/Howchoo/pi-power-button
https://github.com/jeff89179/pi-power-button
