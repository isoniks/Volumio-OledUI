# Attention!
Work in progress, don't use it now ...

# Purpose
The purpose of this fork is to strip All button functionality from original Volumio-OledUI, retaining only dispaly functionality, and make work with Python3.
I'm going to use the product to retrofit my old Yamaha PianoCraft with modern RPi, DAC and OLED screen.


## hardware
* Raspberry Pi 2B/3B with Volumio2 image
* 3.2" 256x64 Pixels 4-wire SPI OLED Display with SSD1322 controller IC (e.g. ER-OLEDM032-1W)
* Optional PCM51x2 DAC


## dependencies
* [socketIO-client](https://pypi.org/project/socketIO-client/)
* PIL
* [luma.oled](https://luma-oled.readthedocs.io/)

## install
get [ssh access to Volumio](https://volumio.github.io/docs/User_Manual/SSH.html), login
and
enable SPI bus by adding
```
dtparam=spi=on
```
to /boot/userconfig.txt

### installation steps
```
git clone https://github.com/isoniks/Volumio-OledUI.git
chmod +x ~/Volumio-OledUI/oledui.py
sudo cp ~/Volumio-OledUI/oledui.service /lib/systemd/system/
sudo systemctl daemon-reload
sudo systemctl enable oledui.service
reboot
```

### how to check the logs
```
sudo journalctl -fu oledui.service
```
# Credits & Kudos
* @Machine2501 for https://github.com/Maschine2501/NR1-UI
* @diehardsk for https://github.com/diehardsk/Volumio-OledUI
