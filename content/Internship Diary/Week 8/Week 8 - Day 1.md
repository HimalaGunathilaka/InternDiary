> [!success] Report
> - Change all server ---- extension connecting mqtt to websockets.
> - Now you can login to other accounts and the blocked list changes accordingly. (No logged out functionality though)
> - Stop mqtt when user is not logged in.
> - Fixed bugs associated with the username. (On start it was not `Guest` when the server is down.)

---
# HTTPS
- Need a SSL certificate to for the website.
- There are free (https://letsencrypt.org/) and non-free ways to get it.

---
![[Pasted image 20260127122920.png]]

---
# CURL
- Create user
```bash
curl -X POST http://localhost:8080/add-user \
  -H "Content-Type: application/json" \
  -d '{
    "username": "testuser",
    "password": "testpass",
    "email": "testuser@example.com"
  }'
```
- Login user
```bash
curl -X POST http://localhost:8080/login \
  -H "Content-Type: application/json" \
  -d '{
    "username": "testuser",
    "password": "testpass"
  }'
```
- JWT
```bash
{"accessToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiJ0ZXN0dXNlciIsImlhdCI6MTc2OTUwMjA1NywiZXhwIjoxNzY5NTA1NjU3fQ.R8G8fUQ6sAYH0jp2v3498Z_gzAJgyo1DLax3N8O-0v8"}
```
- For testing
```bash
TOKEN="PASTE_JWT_HERE"
```
- Add url
```bash
curl -X POST http://localhost:8080/url/add \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "url": "youtube.com"
  }'
```
- Remove url
```bash
curl -X POST http://localhost:8080/url/remove \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "url": "youtube.com"
  }'
```
---
# Issue
- Total focused time. 
	- Do we need to show the focused time per day. If yes there should be a mechanism to trigger a function to send the total focused time after a day.
---

