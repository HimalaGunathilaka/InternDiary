 # Before selling
- All data from ESP32 need to be removed. (Clean reset to remove saved files in production.)
- Extension + ESP32 mqtt address should be changed from test server to production one.
- Current server is on local. Need to publish it in cloud. 
- Mongodb (or any db) may need increase in storage. (Not critical)

# After selling
![[Pasted image 20260202193745.png]]


---
# Components
- ESP32 devkit v1
	![[Pasted image 20260212134837.png|300]]
- Rotary encorder with switch --> https://new.robolabs.lk/product/ky-040-rotary-encoder-module-with-push-switch/
	-> https://www.duino.lk/product/rotary-encoder-module-ky-040/
	![[Pasted image 20260212144450.png|300]]
- Buzzer --> https://www.duino.lk/product/active-buzzer-12v-alarm-sounder/
- Charger (TPU4056) -> https://manuals.plus/asin/B071RG4YWM?utm_source=chatgpt.com
	![[Pasted image 20260212145748.png|300]]
-  (addressible leds) (https://cdn.sparkfun.com/assets/e/6/1/f/4/WS2812B-LED-datasheet.pdf)
	- Non water proof (WS2812b) --> https://www.duino.lk/product/ws2812b-non-waterproof-addressable-led-strips/
	- Water proof (WS2812) ---> https://tronic.lk/product/waterproof-led-strip-ws2812-addressable-pixel-led-60pcs