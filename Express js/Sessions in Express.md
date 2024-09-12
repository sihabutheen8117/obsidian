

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

```
request.session.visited = true ;
```

after run this it wont generate new session id for existing user (currently logged in user.)

you can get any user session data from session store by using session id
```
request.sessionStore.get(request.session.id , (err,data)=>{
	if(err)=>{
		console.log(err)
		throw err;
		}
	console.log(data)
})
```

this value equvalent to "request.session";


---------------

### Store the sessions in Monogdb

##### Why we should stores the sessions ?
- assume that you loggin in the web site after some times one or 2 seconds server goes down ,it will erase all the sessions in the memory.
- so ,after server come back the server ,forgot your session ,so you need to re login the website.
- to prevent this we need to stores the session in the database.

```
npm -i connect-mongo
```

import mondoStore from connect-mongo

in the sesion

```
app.use(session({
	secret :"encoding password",
	saveUnInitialized : false ,
	resave : false ,
	cookie : {
		maxAge : 100 /miliseconds
	}

	//new
	store : mongoStore.create({
		client : mongoose.connection.getClient()
	})
}))
```

- saveUnInitialized : is set to false ,if it is true when ever you visit the site it will automaticcally create and stores the sessions in mongodb database , eventhough user not authendicated.
- resave : is set to false , if it is true , when ever you visit the website it automatically ,set the expirary time to initial value , so it will start from first ,so we do not need them.

