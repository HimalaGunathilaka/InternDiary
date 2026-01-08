
> [!success] Report
> - Put back the LED logic back to ESP32.
> - Total focus time time is synchronized across the browsers.
> - Focus mode is synchronized across the browsers.
> - Make [[ESP32|ESP32]] architecture diagram

# CPP
- **`strtok`** is a C standard library function used to split a string into tokens using specified delimiters. It modifies the original string by replacing delimiters with the null character (`'\0'`) and returns one token at a time.
```cpp
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "C programming is fun";
    char *token;

    token = strtok(str, " ");
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, " ");
    }
    return 0;
}
```
- **`atol`** is a C standard library function used to convert a string into a `long int`. It reads the string until a non-numeric character is encountered and returns the corresponding long value. If the string does not start with a valid number, it returns `0`.
```cpp
#include <stdio.h>
#include <stdlib.h>

int main() {
    char str[] = "12345";
    long int num;

    num = atol(str);
    printf("%ld\n", num);

    return 0;
}
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
> - [ ] IP needs to be fixed.
> - [ ] 30- minutes for one session *
> 	- [ ] Show celebration after one session
> - [ ] Circle display current session 
> - [ ] 1 minute break * (tommorrow demo)
> - [ ] Bottom must display total accumulated time *
> - [ ] Mongodb to share the blocked list (to synchronized) *
> 	- [ ] store accumulated total time for each day
> 	- [ ] but the system should work even work without 
> - [ ] MQTT details should be saved and tried.
> - [ ] MQTT static page button should submit the details. Not the physical button. (But if can't be reconnected after some time publish the page back VS having a physical button.)


