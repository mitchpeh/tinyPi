#Waveshare 3.2” screen
Also sold as a Spotpear screen, this screen connects to the GPIO pins of the Pi, and sometimes comes included with an acrylic case designed to fit the screen. 

Once you have access to the command line, enter the following:
```
git clone https://github.com/mitchpehora/tinyPi
cd tinyPi/waveshare/ss32/
tar xvf LCD-show-32.tar.gz
cd LCD-show/
sudo ./LCD32-show
 ```
Now, the GUI is on the touchscreen. AUDIO DOES NOT WORK

To switch back to HDMI, enter
```
cd tinyPi/waveshare/ss32/LCD-show/
sudo ./LCD-hdmi
```
NO AUDIO.
