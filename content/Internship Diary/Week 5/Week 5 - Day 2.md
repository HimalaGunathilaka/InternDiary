> [!success] Report  
> - MQTT server logic now runs **alongside** the static web browser.

---

## [[Anchors#Internet|Network Interfaces]]

```bash
hostname -I

""
10.10.25.57 # main local IPv4
172.17.0.1 # Docker network
172.19.0.1 # Docker custom bridge
172.18.0.1 # Another docker dridge
2401:dd00:10:20:cdc5:796a:8393:3e5d # IPv6 global 
2401:dd00:10:20:9242:3602:895c:cbed # Another IPv6 global
""
```
---
# [[Anchors#C++|C++]]
- "`.c_str()`" ---> A method of "`std::string`" class that returns a "`const char*`" pointer to a null-terminated C-style string.
- Compare strings --->
```cpp
if (strcmp(msg, "activate") == 0)
```
- Compare first `n` characters ---> 
```cpp
if (strncmp(msg,"d|",2)==0)
```

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
