> [!success] Report
> - Made the MQTT details harcoded.
> - Made a session end signal that will be transmitted after a predefined time interval.
> - Verified node-crone job whether it is publishing data in a specific time.
> - Fixed bugs with server + session end
> 	- On start there were some inconsistencies between the block list in the local and the database. (Found the issue in race conditions of mutex variables)
> 	- Session complete signal was sent multiple times if multiple browsers are open. It was solved by allowing only one browser to publish session end.


---
# MongoDB shema for one user
```json
{
"userId":"ojohp",
"blockList":["jaoej","ajfowej","kajewofj",...],
"total_time":["dd-mm-yyyy":0,...],
"numberOfSessions":[{"dd-mm-yyyy":3},...]
}
```
