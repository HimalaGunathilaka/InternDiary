> [!success] Report
> - Made a simple login register page and connect that to a button (`Gues`) to open in a new tab.
> - User can register and create a new user. But need email and username (Have to discuss if both needed.)
> - A jwt will be given for successful login. (Currently no session time checking logic is not implemented yet.)
> - The guest button shows the username on successful login.
> - Currently `http` is used later `https` transformation is needed.

---
# UI
![[Pasted image 20260123194601.png]]![[Pasted image 20260123194730.png]]![[Pasted image 20260123194614.png]]
![[Pasted image 20260123194625.png]]
![[Pasted image 20260123194715.png]]



---
# JWT

- To generate random string for token
```js
node -e "console.log(require('crypto').randomBytes(32).toString('base64'));"
```


## CURL
```bash
curl -X POST http://localhost:8080/add-user \
  -H "Content-Type: application/json" \
  -d '{"username":"testuser","password":"123456"}'
```
