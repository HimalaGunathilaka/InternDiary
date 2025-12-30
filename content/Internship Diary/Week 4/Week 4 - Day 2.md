> [!success] Report
> - Displayed number of minutes on the 7 segment display.
> - Correctly identifies each focus time from different browsers. (Each browser focus time has a random id.)

---
# Design decisions
- To display the cumulative focus time, each and every browser focus time need to be identified separately. 
- My current implementation involves, sending focus time on deactivate signal with a unique browser id. 
- Inside ESP32 there will a hash table. Every time it receives a deactivate signal, it will assign the focused time in relevant space gotten by the hash of the key.
- After every deactivate event total existing time in the hash table is taken to a sum and then displayed.
- Concern exist regarding the uniqueness of the browser id. Current implementation is a random number generation.
---
> [!warning] Issues and To do
> - Having a seperate server for monitoring time.
> - If 8 LEDs present to show number of times focus button was pressed, what happens when a 9th press happens. Should it reset the LEDs. What does the LEDs actually represent?
> - The random id need to be updated such that it will not cause overlaps.

---
# Update video
https://drive.google.com/file/d/1NMDTCFayL4ONr1xttyN9jVH_xEK4HZlB/view?usp=sharing



