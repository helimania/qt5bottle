# QT5Bottle by Blackheart dev.
QT 5.12.2 EGLES Bottle for Raspbian Buster Lite without installations and compilations

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

# First Raspberry PI boot

Set root password:
```ruby
sudo passwd root
```
Set pi password:
```ruby
sudo passwd pi
```
Run Raspbian configurator and enable SSH and setup WiFi
```ruby
sudo raspi-config	
```
If desired, remove all strings from motd
```ruby
sudo nano /etc/motd
```
If desired, enable SSH root access: PermitRootLogin yes
```ruby
sudo nano /etc/ssh/sshd_config	
```
At end of cmdline.txt add: quiet splash loglevel=0 logo.nologo
```ruby
sudo nano /boot/cmdline.txt
```
Update RPI firmware and reboot
```ruby
sudo rpi-update
sudo reboot
```

# Second Raspberry PI boot
The following steps can be done localy on Raspberry PI or over SSH

If desired, login as root and change usernam and home path from pi
```ruby
usermod --login newusername --move-home --home /home/newusername pi && groupmod --new-name newusername pi
```
Now you can login as newusername.

Uncomment deb-src on sources.list
```ruby
sudo nano /etc/apt/sources.list
```
Update Raspberry PI software and rebut
```ruby
sudo apt-get update && sudo apt-get upgrade -y
sudo reboot
```

# DT5Bottle installation

Installation time will take no more than 5 minutes
```ruby
wget https://raw.githubusercontent.com/helimania/qt5bottle/main/qt5bottle.install.sh
chmod +x qt5bottle.install.sh
sudo ./qt5bottle.install.sh
```
This script automatically download QT5Bottle and set up the necessary environment for running applications through EGLES
