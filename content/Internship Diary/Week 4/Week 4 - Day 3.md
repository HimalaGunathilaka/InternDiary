> [!success] Report
> - Updated popup UI to show website icons to of the blocked list. Plus a reset button to reset total focus time. A circular progress bar was made to show how much time out of 8 hours user has focused. 
> - An alarm was made to reset the timer after midnight.
> - Some bugs related to add button were fixed.

---
# [[Anchors#CSS|CSS]]
- Viewport height ----> It’s how tall the screen space is where the webpage is shown (not the whole page, just what you can see).	
	- `vh` = **viewport height**
	- `1vh` = **1% of the browser window’s height**
	- `100vh` = **the full visible height of the screen**
```css
/* x-offset, y-offset, blur, spread */
box-shadow: 6px 6px 10px -1px;
```
- Spread defines how far the shadow expands or contracts from the element’s edges.

# [[Anchors#Internet|JS usefull]]
- To get icons from host urls. Use following favicon based function.
```js
chrome.storage.local.get("block", (data) => {
  const blocked = data.block ?? [];
  // Toggle button state
  addBtn.classList.toggle("tag", blocked.includes(hostname));
  // Clear old icons
  iconContainer.innerHTML = "";
  blocked.forEach(site => {
    console.log(site); // site is a string
    const img = document.createElement("img");
    // OPTION 1 (recommended): Google favicon service
    img.src = `https://www.google.com/s2/favicons?sz=64&domain=${site}`;

    // OPTION 2 (less reliable)
    // img.src = `https://${site}/favicon.ico`;
    img.alt = site;
    img.title = site;
    img.width = 32;
    img.height = 32;
    iconContainer.appendChild(img);
  });
});

```
	
	- Here icons from blocked list are being fetched and rendered inside a <div> tab inside the html page.

# Enclosure
![[Pasted image 20251231174323.png]]


# Reddit ideas
- https://www.reddit.com/r/SideProject/comments/1mpby7n/im_making_an_app_that_blocks_social_media_until/
- https://www.reddit.com/r/dumbphones/comments/1q081me/has_anyone_figured_out_a_way_to_break_the_tiktok/

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

