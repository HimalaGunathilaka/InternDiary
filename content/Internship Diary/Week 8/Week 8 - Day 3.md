> [!success] Report
> - Made a multicast DNS for the esp32. (Basically I don't need the ip of the esp32 now.)
> - Now when esp32 connect to network epsBtn shows `connected` and when it is not it will show `disconnected`. (Need to verify how newly given device behave. For now every time espBtn is pressed esp32 will publish its device id.)
> - Made all the time `00h : 00min` format.
> - Change color pallet. (Not fixed yet.)

---
# MDNS (Multicast DNS)
- https://medium.com/engineering-iot/understanding-mdns-on-esp32-local-network-device-discovery-made-easy-9aab590f0eea

---
# MQTT last will
```cpp
// MQTT Last Will & Testament (LWT)
// This message is automatically published by the broker
// if the ESP32 disconnects unexpectedly (power loss, WiFi drop, crash)
client.connect(
    "ESP32Client",          // Client ID (must be unique per client)
    mqttUsername.c_str(),   // MQTT username
    mqttPassword.c_str(),   // MQTT password
    "esp/status",           // LWT topic (where disconnect status is published)
    1,                      // LWT QoS (delivery guarantee level)
    true,                   // LWT retained (broker keeps last status)
    "offline",              // LWT message (published on unexpected disconnect)
    false                   // cleanSession = false (persistent session)
);

```



---
![[Pasted image 20260129124614.png]]![[Pasted image 20260129131320.png]]![[Pasted image 20260129131423.png]]