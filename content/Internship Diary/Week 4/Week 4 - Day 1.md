>[!success] Report
>- Downloaded a full script of paho mqtt implementation and got it approved by manifest.
>- Use MQTT instead of websocketting for extension.
>- ESP32 is connected to MQTT as well.

---
- The **`DOMContentLoaded`** event fires when the HTML document has been completely parsed, and all deferred scripts ([`<script defer src="…">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/script#defer) and [`<script type="module">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/script#module)) have downloaded and executed. It doesn't wait for other things like images, subframes, and async scripts to finish loading.
---
# Paho mqtt
- Following to download the whole paho library to a file.
```bash
wget https://cdnjs.cloudflare.com/ajax/libs/paho-mqtt/1.0.1/mqttws31.min.js
```

---
# VS code
- To reload the vscode windows.
```
ctrl + Shift + P

Developer: Reload Window
```

---
# MQTT
	- 1883 → embedded / IoT devices (ESP32, sensors)
	- 9001 → high-level applications / web / extensions
- Some definition says MQTT need two ports to provide unecrypted data and secure (TLS) data.
## KeepAlive mechanism
- You can set a keep alive mechanism ---> Client send `PINGREQ` ------> A PINGRESP get received.

---
# Docker 
```bash
docker exec -it <container_id_or_name> /bin/sh
```
- Command to run a command inside a running container.
- `-i` --> interactive mode
	- Keeps **STDIN open** so you can type commands into the container.
- `-t` ---> terminal mode
	- Allocates a **pseudo-TTY**, so you get a terminal interface that behaves like a normal shell.

---

>[!warning] Todo and Bugs
>- Formal specification of the system. (Hardware and software.)
>- Reset time doesn't works. 

>[!abstract] Assign works
> - [ ] 8 led --> Day
> - [ ] synchronization ---- between extension (not critical)
> - [x] sync total accumulated time and display it
> - [ ] add , remove should be sperated
> - [ ] enclosure ideas --> reactive to user
> - [x] display total accumulated time on hardware display perday
> - [ ] configure username and password for Wifi----else
> - [ ] focusMode on --> (red light) else (green light)
> - [ ] identify requirement for publishing
