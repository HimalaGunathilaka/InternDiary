> [!success] Report
> - Popup can add and remove urls from the mongodb database.
> - On browser startup all the urls are fetched from the database if the mqtt connection and the server connection exist.
> - Session is limited to 25 minutes from now. But deactivation reset the timer on the circular progress bar. 
> - Total time is displayed.
> - Updated [[Extension|flowchart]]
> - Updated [[ToDo]]


---
# Format of one customer document in a mongodb collection
```json
/** 
* Paste one or more documents here
*/
{
  "url": "chatgpt.com",
  "userId": "ojpihp",
  "urls": [
    ""
  ]
}
```
