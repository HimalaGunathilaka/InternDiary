> [!success] Report
> - Made a mongodb database for the server.
> - Made a MQTT requests to handle data submission, deletion and fetching from the database for the block list for now.

---
# MongoDB data
![[Pasted image 20260109173713.png]]
![[Pasted image 20260109173800.png]]

---
# Linux stuff
- `wget`  ----> A powerful non interactive command-line utility for downloading files from the web using HTTP, HTTPS and FTP.
- To find the operating system
```bash
lsb_release -a


//
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 24.04.3 LTS
Release:	24.04
Codename:	noble
//
```
---
# Node js
- First initialize the directory to set up `packge.json`
```bash
npm init -y
```

### package.json VS package-lock.json
- **`package.json`** ---> Node.js project's metadata and general dependancies.
- **`package-lock.json`** -----> Locks the exact installed version of every dependency to ensure consistent and reproducible installs across different environments.
---
# Mongodb
- Recently found vulnerability 
	```lua
	MongoDB
 └── Database
      └── Collection
           └── Document
                └── Field
	```


|MongoDB|SQL|
|---|---|
|Database|Database|
|Collection|Table|
|Document|Row|
|Field|Column|
- **MongoClient** ---> is the main class provided by the official MongoDB node.js driver. It is a essentially your **gateway to the MongoDB server**. Through it,
	- Connects to a MongoDB instance or cluster
	- Select databases and collections
	- Run queries 
	- Manage connections (open, close, pool connections)
- ==**Connection** = a live TCP link between your app and the MongoDB server==
- MongoDB supports **connection pooling**, where one `MongoClient` keeps multiple connections alive and reuses them for multiple operations.

---

# [[ToDo|ToDo]]
- Make C4 diagrams
- Make sequence diagrams
