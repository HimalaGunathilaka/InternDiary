> [!success] Report
> - Configured wifi manger to put wifi credentials from outside.
> - Made a simple web server to capture MQTT details.


# [[Anchors#ESP32|WiFi manager]]
- `When your ESP32 is in STA mode (station mode), it acts like any other device, such as your laptop or smartphone, that wants to connect to an existing Wi-Fi network.`
- `When your ESP32 is in AP mode (Access point modde), it creates its own Wi-Fi network, assigning it an SSID (the network’s name), a password, and an IP address.`
- Using [WiFiManager](https://github.com/tzapu/WiFiManager.git) by tzapu.

> [!note] Process
> 1. ESP starts.
> 2. Set up as ==Station mode== and tries to connect to previous saved.
> 3. If unsuccessful it moves the ESP to ==Access point mode== and spins up a DNS and webserver (default ip <span style="color:rgb(256, 0, 0)">192.168.4.1</span>)
> 4. By going to the ip you will get a website which shows the scanned networks already available. You can select and save one of them.

|Stage|What happens|
|---|---|
|WiFiManager AP mode|ESP acts as router + config page|
|WiFi connected|ESP joins real WiFi|
|MQTT connect|Only AFTER WiFi is connected|

---
### [[Anchors#ESP32|How to reset a ESP32]]
```bash
pip install esptool

python -m esptool --chip esp32 --port YOUR_PORT_NAME erase_flash
```

- To get the port name
```bash
ls /dev/ttyUSB*
```

or
```bash
pio run --target erase
```

---
> [!warning] Issues and Todo
> - Haven't integrated wifi manager and esp32 server to the project yet.
> - Need to study about the mqtt broker. For now local ips only the one I used.
> - 




---
# Video
https://drive.google.com/file/d/1alGyg_sBHu5qTdBq1e87zfF5wVXLSptI/view?usp=sharing

---

>[!abstract] Assign works
> - [ ] 8 led --> Day
> - [ ] synchronization ---- between extension (not critical)
> - [x] sync total accumulated time and display it
> - [ ] add , remove should be sperated
> - [ ] enclosure ideas --> reactive to user
> - [x] display total accumulated time on hardware display perday
> - [x] configure username and password for Wifi----else
> - [ ] focusMode on --> (red light) else (green light)
> - [ ] identify requirement for publishing
> - [ ] Block user from changing block list when focusMode is on
> - [ ] Go with image color pallet
> - [ ] Remove website url when clicking on the icon and remove the icon as well


