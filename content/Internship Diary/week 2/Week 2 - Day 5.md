# Wesocketing technicle details
## 1. WebSockets must be polled frequently
- WebSockets are NOT interrupt-based
- `client.poll()` must run many times per second
- If polling stops → ping/pong missed → disconnect

Rule:
> Never block the loop

---

## 2. `delay()` breaks networking
- `delay()` pauses WiFi, TCP, and WebSocket handling
- Even small delays (100–300 ms) can drop connections

Rule:
> Use `millis()` timers, never `delay()`

---

## 3. `available()` ≠ connected
- `available()` only means "data is waiting"
- It does NOT indicate connection state

Rule:
> Never use `available()` to detect disconnects

---

## 4. Disconnects are event-driven
- WebSocket libraries notify disconnects via events
- `ConnectionClosed` is the only reliable signal

Rule:
> Clean up clients ONLY in `onEvent(ConnectionClosed)`

---

## 5. Always clean up WebSocket clients
- Leaving old clients causes memory leaks
- Prevents clean reconnections on ESP32

Rule:
> On disconnect: `close()` → `delete` → `nullptr`

---

## 6. Single source of truth
- Core state (e.g., `focusMode`) must live on ESP32
- Clients send intent, ESP32 decides state

Rule:
> One source of truth prevents desync

---

## 7. Reconnects must be explicit
- Browsers reconnect aggressively
- ESP32 must accept and replace old connections cleanly

Rule:
> Kill old client before accepting a new one

---

## 8. Fast loop = stable system
A healthy ESP32 loop:
- Polls WebSocket
- Handles flags
- Updates hardware
- Exits immediately

Rule:
> A boring, fast loop is a stable loop

---

## Mental Model
WebSockets on ESP32 are like a bicycle:

> It stays upright only while moving  
> Stop polling → it falls (disconnects)



# Doughts
- To keep the websocket active, the connection must not be at idle. Therefor I implement a ping pong mechanism for every 1.5 seconds. But considering whether I should move to BLE instead of wifi.
- Formal specification of number of LEDs, number of focus button presses per day, cool off time delay (for now 1 minute)

# Issues and bugs to be fixed
- Focus time isn't being reset.
- ESP32 doesn't cause the meme to popup.
- Bugs with appearing of meme.


# Progress video

https://drive.google.com/file/d/1fNveHbOa1TedHp3y_9ESkwWhWqCE8Lzm/view?usp=sharing
# Demo video

https://drive.google.com/file/d/1ppgbfz9_7kiX3m76FZ6CApZSEAdYQwF2/view?usp=sharing

