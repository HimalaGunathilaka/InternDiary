> [!success] Report
> - A button is added which shows whether current active tab's website is on focus list or not. Can add it to list by clicking the button.

---
# URLs
![[Pasted image 20251223121821.png]]
- A URL starts with a protocol that is used to access the resource on the internet. The resource is accessed through the [Domain Name System](https://www.geeksforgeeks.org/system-design/whats-is-domain-name-systemdns/) or DNS. There are multiple protocols avaiable to use like [HTTP](https://www.geeksforgeeks.org/blogs/http-full-form/), [HTTPS](https://www.geeksforgeeks.org/html/explain-working-of-https/), [FTP](https://www.geeksforgeeks.org/computer-science-fundamentals/file-transfer-protocol-ftp/), mailto, [TELNET](https://www.geeksforgeeks.org/computer-networks/introduction-to-telnet/) etc.
- JS already has a way to extract the domain.

---
# Scaling Up the System

- As the extension is expanded to support multiple devices and applications, the system’s **single source of truth** (i.e., whether `focusMode` is ON or OFF) ==must be centralized==. Without this, state divergence across clients can lead to inconsistent behavior and misinterpretations.
- A **publish–subscribe architecture** is well-suited for this scenario, as it enables all clients to react to state changes in real time while remaining loosely coupled.
- I propose using **MQTT** as the messaging protocol, hosted on a broker such as **Mosquitto**, to efficiently broadcast focus state updates across devices and applications.

## Comparison

| Feature / Aspect                 | Current WebSocket Implementation                                              | MQTT Implementation                                                                   | Impact of Switching to MQTT                                       |
| -------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **Architecture**                 | Point-to-point                                                                | Publish–subscribe,                                                                    | Centralized state, reduces misalignment between devices           |
| **State Management**             | Each connection maintains its own state; risk of inconsistency across devices | Broker maintains the last retained message; new clients immediately get current state | Ensures a single source of truth; simplifies multi-device sync    |
| **Scalability**                  | Limited; server must track all connections manually                           | Highly scalable; broker handles multiple clients and topics                           | Easier to add more devices or apps without modifying server logic |
| **Message Delivery**             | WebSocket delivers messages immediately to connected clients                  | MQTT supports QoS levels (0, 1, 2) for guaranteed delivery                            | Reduces message loss; ensures clients receive critical updates    |
| **Connectivity**                 | Requires persistent connections; disconnected clients miss updates            | Broker handles reconnects and can retain messages for offline clients                 | More robust to network instability and device reconnections       |
| **Complexity of Implementation** | Simpler for a single server and few clients                                   | Slightly more setup (broker, topics) but scales better                                | Slight upfront cost, long-term reliability gain                   |
| **Real-Time Performance**        | Very low latency; direct push from server to clients                          | Low latency, slightly more overhead due to broker                                     | Negligible difference for typical UI/state updates                |
| **Security Options**             | Depends on WS/WSS setup; must handle individually                             | MQTT can use TLS, username/password, ACLs for topics                                  | Centralized security control; easier to enforce policies          |


---
# Goals
- [x] Architecture design for multiple device synchronization.
- [x] Update add url to capture the home website.
- [ ] Put a icon on extension.

# Issues and todo
- Improve add url button behavior. 
- Blocking the website just after pressing the button.

# Doubts
- ==How should the UX for the url add button should works out.==
- Formal specification of number of LEDs, number of focus button presses per day, cool off time delay (for now 1 minute)
- Does the blocking mechanism works for desktop apps as well. (Like youtube app in windows)