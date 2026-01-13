> [!success] Report
> - MQTT configuration details are now being saved between resets and power offs.
> - A cron job similar library (node-cron) was implemented to reset the total time and to save up the date and time of the total time in mongodb.
> - Updated [[Decisions#Static IPs|Decisions / Static IPs]].

---
# preference.h <---- A file management library
- https://espressif-docs.readthedocs-hosted.com/projects/arduino-esp32/en/latest/api/preferences.html#overview
- Now if the previous details for mqtt server exist it will automatically connects.
- ==But I have not remove the physical button. When pressed it will activate http request handling for the mqtt form page.==
---
# node-cron
- https://nodecron.com/getting-started.html

