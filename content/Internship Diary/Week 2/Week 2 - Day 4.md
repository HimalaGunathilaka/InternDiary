# Java script
  
 ```js
  // -------------------- Redirect logic --------------------
async function enableRedirectRules() {
	await chrome.declarativeNetRequest.updateDynamicRules({
		removeRuleIds: [REDIRECT_RULE_ID],
		addRules: [
		{
			id: REDIRECT_RULE_ID,
			priority: 1,
			action: {
				type: "redirect",
				redirect: { extensionPath: "/focus.html" }
		},
		condition: {
			urlFilter: "*",
			resourceTypes: ["main_frame"]
		}
	}
	]
	});
		//console.log("Redirect rules enabled");
}
//--------------------------------------------------------
  resourceType: ["main_frame"]
  
  // and
  declarativeNetRequest
  ```
  - only affects network requests in general. Therefor they can't check the already existing site.


| Scenerio                                                    | What happens       |
| ----------------------------------------------------------- | ------------------ |
| You type `youtube.com` and press Enter                      | ✅ Redirect happens |
| You click a link to `youtube.com`                           | ✅ Redirect happens |
| You are _already_ on `youtube.com` when the rule is enabled | ❌ Nothing happens  |
- No new `main_frame` request is made.

---
# Fetching current tabs
- To fetch current active window and tab,
```js
chrome.tabs.query({ active: true, currentWindow: true })
```
- To fetch all tabs,
```js
chrome.tabs.query({})
```
---
# JS objects
- JS objects needs to be key value pairs.
- Else use ,
```js
object = name: "Himala"}

// Retrieve them by
object.name
object["name"]

arrya = [1, 2, 3]
```

```
{} <---- function body
```
---
## `??` — the **nullish coalescing operator**

- Syntax: `a ?? b`
- Meaning: _“If `a` is `null` or `undefined`, use `b` instead.”_
- Unlike `||`, it **doesn’t treat `false` or `0` as “empty”**.





---
>[!note] Todos and bugs
>- Image showing logic issue.
>- ESP32 and popup doesn't keep constant connection.
>- <span style="color:red">Need formal specification on number of LEDs and Number of button press. Reset time.</span>
>- ESP32 doesn't cause meme to popup
>- Icon for the extension



