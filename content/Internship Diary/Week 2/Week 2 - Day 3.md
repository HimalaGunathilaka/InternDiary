# Need to be dealt with

- Only when typed the url and search the redirecting triggers. 
	- Does not happens when already inside youtube. 
	- Also when already inside youtube and click on a video is also accessible.
- URLs are not select-able only hard coded.
- ESP32 button cool off has not yet built.

# PlatformIO issue with Linux
- If vscode extension is stuck on installing or initializing and asking for python intrepreter install following.
```bash
sudo apt install python3-venv
```
- Here we have pip + setuptools.
- Ubuntu now (24.04) ships python as externally managed.
- Tools like platformIO relies on,
	- venv
	- pip
	- setuptools
	- wheel
- Do not install platformIO via Conda.


<div style="page-break-before: always;"></div>

## If uploading didn't worked due to permission error
```bash
newgrp dialout
sudo usermod -aG dialout $USER
```
- For using usb by platformIO.
```bash
sudo apt install curl

curl -fsSL https://raw.githubusercontent.com/platformio/platformio-core/develop/platformio/assets/system/99-platformio-udev.rules | sudo tee /etc/udev/rules.d/99-platformio-udev.rules
sudo udevadm control --reload-rules
sudo udevadm trigger

sudo usermod -aG dialout $USER

# Check
ls -l /dev/ttyUSB0

```


<div style="page-break-before: always;"></div>

# Current mapping of the LED grid

![[Pasted image 20251217135800.png]]


<div style="page-break-before: always;"></div>

# User flow diagrams
![[Blank diagram - Page 1(1).png | 400]]

![[Blank diagram - Page 1.png | 400]]


<div style="page-break-before: always;"></div>

# ESP32 Logic flow chart

![[esp32 - Page 1.png]]

![[esp32 - Page 1(1).png | 400]]


<div style="page-break-before: always;"></div>

# Website

![[website - Page 1.png]]

![[website - Page 1(1).png]]

![[website - Page 1(2).png]]

![[website - Page 1(3).png]]


# Todo next day
- Make blocking url configurable.
- Add a meme when you try to deactivate the before the cool off time.
- Fix the cool off time for ESP32.
- Block website when already on that page.