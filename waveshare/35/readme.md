#Waveshare 3.5 screen

Also sold as a Spotpear screen, this screen connects to the GPIO pins of the Pi, and usually comes included with an acrylic case designed to fit the screen. You will need to follow (slightly) different instructions for different Linux kernels. Access the command line either through your OS, or through SSH and use the common `name -r` to determine which kernel you are running.

Once you have access to the command line, enter the following:
```
git clone https://github.com/mitchpeh/tinyPi
 ```

For kernel 4.4 or newer:
```
sudo cp tinyPi/waveshare/35/waveshare35a-overlay.dtb /boot/overlays/waveshare35a.dtbo
```

For kernel 4.3 or earlier:
```
sudo cp tinyPi/waveshare/35/waveshare35a-overlay.dtb /boot/overlays/
```
Then, open the `config.txt` file:
```
sudo nano /boot/config.txt
```
Uncomment `dtparam=spi=on` (remove the #), and add `dtoverlay=waveshare35a` to the file, then `control+x` to exit, `y` to save changes, then `enter`. Reboot using `sudo reboot`. Once it reboots, enter `ls /dev/fb*`.

If `/dev/fb1` doesn’t show up, you’ll have to start over. Make sure you copied everything correctly. then, enter the following commands:
```
sudo apt-get install cmake
cd tinyPi/rpi-fbcp
mkdir build
cd build/
cmake ..
make
sudo install fbcp /usr/local/bin/fbcp
sudo nano /etc/rc.local
```

Add `/usr/local/bin/fbcp &` before the `exit 0` line, then `control+x` to exit, `y` to save changes, then `enter`. Reboot. You should now have an image on the touchscreen, and an image on your HDMI display.