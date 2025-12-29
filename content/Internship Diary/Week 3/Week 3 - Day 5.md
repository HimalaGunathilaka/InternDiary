>[!success] Report
>- Initialize a mqtt server in local in a docker container.
>- Made a icon for the popup.

---

# Adding a icon to extension
- Following should be added to the manifest.json 
Chrome uses your extension icon in **different UI contexts**, and each one expects a different size for sharp rendering.

|Size|Used for|
|---|---|
|**16×16**|Extension list, menus, small UI|
|**32×32**|Toolbar icon (standard / normal DPI)|
|**48×48**|`chrome://extensions` page|
|**128×128**|Chrome Web Store, large displays, details view|

---

# Docker notes
```bash
docker compose up -d
```

- `docker compose` ---> Read compose.yml or docker-compose.yml in current directory.
- `up` ----> Create and start everything defined in that file.
- `-d` ---> Run in the background. (detached)
# Setting up mqtt
- From https://support.atmotube.com/en/articles/10449916-setting-up-a-local-mqtt-environment
```bash
docker run -it -d --name mqtt -p 1883:1883 -p 9001:9001 -v /mosquitto/mosquitto.conf:/mosquitto/config/mosquitto.conf eclipse-mosquitto
```
- To check what is the port is held by 
```bash
sudo lsof -i :PORT
```
- New subscriber
```bash
mosquitto_sub -h localhost -p 1883 -t test/topic -u USERNAME -P PASSWORD -v
```
- New publisher 
```bash
mosquitto_pub -h localhost -p 1883 -t test/topic -m "AUTH WORKS" -u USERNAME -P PASSWORD
```
- Username in here is for the username set-upped in the configuration.

## MQTT in JS
- There are two methods
	- paho by ecplipse (same guys implemented mosquitto)
	- mqtt.js (more updated)
- Here chosen mqtt.js since it is updated and suited for advance ui functionalities.
- mqtt.js provide inbuilt reconnecting capability.

# JS extension
- Doesnot like imports. The script should contain all. There for use something like webpack to parcel it.
- There something calle `.cjs` which goes for saying common js file. It useful if you specify all files are ES modules in the `package.json` , but need a file not like that.

---

# Todo and issues
- `manifest.json` does not like when packages are imported. Need to pack the packages and upload it.
- So far mqtt.js fail. (suspect inbuilt running eval causing the manifest to hault the script). Need to check with paho for JS as well. (paho and mqtt.js are two ways to get mqtt on JS)
- Formal specification of the system.

---
# Week 3
https://drive.google.com/file/d/1EGu7e108d81hMipUuOK_YrHq_wLSMUe3/view?usp=sharing