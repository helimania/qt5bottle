# qt5bottle
QT 5.12 EGLES Bottle for Raspbian Buster Lite

# Prepare Raspberry PI

Download Raspberry Pi OS Lite from here https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit and flash image to SD Card
```ruby
unzip -p 2021-01-11-raspios-buster-armhf-lite.zip | sudo dd of=/dev/sdX bs=4M conv=fsync status=progress
```
For Sharp lQ123K1lG03 12.3 display, I recommend config.txt settings
```ruby
dtparam=audio=on
disable_overscan=1
hdmi_cvt 1280 480 60 6 0 0 0
hdmi_group=2
hdmi_mode=87
disable_splash=1
```
# FirstRaspberry PI boot

Set root password:
```ruby

```
