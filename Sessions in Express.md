

- https is stateless
- sessions is used to manage user authendication

import session from express
and register in express by
```
app.use(session())
```
- register sessions before routers registration.
- u can pass the secret key inside the sessions
- example

```
app.use(session({
	secret :"encoding password",
	saveUnInitialized : false ,
	resave : false ,
	cookie : {
		maxAge : 100 /miliseconds
	}
}))
```

- what is save un initialized , by default when user visit the site ,it will store the user session id in the server ,even user does not register or login to the website , it consumes more amunt of memory in the server site , so we set to false to store.

How to log and see the ssession data 
```
console.log(request.session);
// it will return object

console.log(request.session.id);
//it will return session id as string
```

when ever visite the site it will generate different session id , eventhough for same user.
- it will be confusion because we want one sessionId for one user not many session ids

