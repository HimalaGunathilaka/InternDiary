# Report
> [!success] Fixed bugs of meme photo
> - Now meme is showing correctly only when the user tries to deactivate focus within cool off. 
> - ESP32 triggers the meme as well

---
- While fixing the bugs so far I have notice common pattern in JS. Its 

  > [!note] [[Anchors#JavaScript|JS behavior]]
>- JavaScript is **event-driven** and **asynchronous by design**.
>- It simplifies **state synchronization** through:
> 	- event listeners
 >	- callbacks / promises
 >	- reactive-style update
> - This design favors:
 >	- responsiveness
 >	- non-blocking execution
>- At the cost of:
>	- additional indirection
>	- possible redundant updates
>	- performance overhead if not structured carefully

> **Trade-off:**  
> JavaScript prioritizes **coordination and responsiveness** over raw execution performance.

---
# [[Anchors#JavaScript|Connecting context between script]]
```js
chrome.storage.onChange.addListener((changes, area) =>{
	if (area !== "local") return;
	
	// Only react when focusMode changes
	if (!changes.focusMode) return;
	
	// Only when focusMode is turned ON
	if (changes.focusMode.newValue !== true) return;
	
	// Check current absoluteFocusmode
	chrome.storage.local.get("absoluteFocusmode", ({ absoluteFocusmode }) => {
	if (absoluteFocusmode === true) {
		displayImage(true);
		}
	});
})
```
### [[Anchors#JavaScript|Notes on `chrome.storage.onChanged`]]
- `onChanged` **does not provide a snapshot of storage**.
- `changes` contains **only the keys that changed** in that update.
- Each changed key has the structure:
```js
{
  oldValue: <previous value>,
  newValue: <current value>
}
```
- If a key did **not change**, it **does not exist** in `changes`.
    - `changes.someKey` → `undefined` (not `null`)

> **Mental model:**  
> `onChanged` gives a _diff_, not the full state.

 ---


# Issues and Bugs
- Add button issue. Sometimes the url does not triggers. Need to check the conditions and adjust them.


# Doubts
- ==How should the UX for the url add button should works out.==
- Formal specification of number of LEDs, number of focus button presses per day, cool off time delay (for now 1 minute)
