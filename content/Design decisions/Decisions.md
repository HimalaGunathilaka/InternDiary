# MQTT
- ==QoS is default for now (QoS = 0)==
- One link at a time is sent from mongodb to server.
- The mqtt details is not being initialize by the wifimanager library since its only triggers when the wifi is not there, which means you can't change the mqtt details unless the wifi changes.
# Static IPs
- I am not using static IPs for now. While it is possible after further studying it is revealed that when you config a ip to ESP32 it will not say to the router to stop that ip from assigning to another device. There for there is a chance of ip conflicts to occur. Otherwise need to configure the router to recognize the ESP32 MAC address all ways as a predefined ip.