# Before selling
- All data from ESP32 need to be removed. (Clean reset to remove saved files in production.)
- Extension + ESP32 mqtt address should be changed from test server to production one.
- If mqtt user password is being used Extension should be able to make a new user in mqtt -----> Then when device is being sold need to include those details along side with mqtt broker.
- Current server is on local. Need to publish it in cloud. 
- Mongodb (or any db) may need increase in storage. (Not critical)

# After selling
![[Pasted image 20260202193745.png]]