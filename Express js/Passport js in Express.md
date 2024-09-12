- is is like to auth the user in secure way.
- it is used to auth user like username and password.
- it managed the sessions. for every user.
- mapping user to express session

installing passport js.
```
npm -i passport passport-local
```
it is local stradegy not any other third party.

import passport from passport,

register using app.use(passport.initialize());
register using app.use(passport.session());

create a stradegy
- create a file for ur stradegy.
- in that file.

```
import passport from 'passport'
import {Stradegy} from 'passport'

export default passport.use(
	new Stradegy({usernameField : 'email'}(username ,password ,done)=>{
		try{
			//find user user from db.
			// if user not found simply ( throw new Error('error message'))
			//user found chech password.
			//password correct then 
			done(null ,user)
		}catch(err){
			done(err ,null)
		}
	}
))
```
- it is the stradegy for ur authendication.
- if u wants to use email as a username which is came from the client side just use username filed and out whatever u want email something like that (it will take email from the req body as a username) , or u want to use username as username just leave it that .
- Done function :  refers done with these ,if err then will pass the error automatically. (default internal server error (500))

- import this file into main file.
- set up (using)
```
app.post( '/url ' ,passport.authendicate("local") ,(req,res)=> {

})
```
- local means we are using local stradegy.

----

In **Passport.js**, `serializeUser()` and `deserializeUser()` are key functions used in session-based authentication, which is common for applications that need to keep users logged in across multiple requests. These functions are essential for managing user sessions after a user is authenticated.

{it will be done before new stradegy}
### 1. **serializeUser()**

- This function is called when Passport is saving user data to the session.
- It decides what user information should be stored in the session.
- Typically, it stores just the **user ID** in the session to keep things lightweight.
- The purpose is to **serialize** or reduce the user object into a minimal format that will fit into a session store.

Example :
```
passport.serializeUser((user, done) => {

  done(null, user.id);  // Save only the user's ID in the session
  
});

```
In this example:

- `user` is the user object obtained after authentication.
- The callback function `done` is called with `null` (indicating no error) and the `user.id`, which is what gets stored in the session.

{ take the user object store it in session data }
### 2. **deserializeUser()**

- This function is used to retrieve the full user object when necessary, such as for making further authenticated requests.
- Passport calls this on every request to restore the user object based on what was stored in the session (i.e., the `user.id` from `serializeUser()`).
- It fetches the full user details by looking up the user ID in the database or another data store.

#### Example
```
passport.deserializeUser((id, done) => {

  User.findById(id, (err, user) => {
  
    done(err, user);  // Pass the full user object to the request
    
  });
//or refer this also

	try{
		//find user with their id 
		//if user not found throw the error.
		//else 
		done(null ,user)
	}
	catch(err){
		done(err ,null)
	}
});

```
In this example:

- The `id` is the user ID retrieved from the session.
- `User.findById(id)` is a typical database lookup to find the user based on the ID.
- Once the user is found, it calls `done` with the full user object, which Passport attaches to `req.user` in subsequent requests.


### Summary of Flow:

1. **Login**: When a user successfully logs in, `serializeUser()` is called, and only the user ID is stored in the session.
2. **Session Usage**: On each subsequent request, `deserializeUser()` is called, retrieving the full user object from the database using the stored ID.
3. **Accessing User Data**: Once deserialized, the full user object becomes available in `req.user`.

Let me know if you want to dive deeper into this with examples or a practical scenario!

----------------

# WORK FLOW OF PASSPORT

#### Read carefully

- passport is a kind of thing which is used to manage the session data ,to client to server side.
- passport is used to authendicate user ,user is existed or not.

- passport has two function ser (serializer ) , deser (deserializer);
- when you logged to the server , passport will execute the stradegy you defined.
- it will return the user data when authendicate successfully , else err.
- when you authendicated serializer function will call execute ,what this function will  do is ,it will attach the user id to the req ,body (session).
- by attaching only user id instead of full user details ,it will optimized. (id should be unique)
- after logged in , whenever you make another api call , it will executer deserializer , it will get back your data using user id ,which is previously attached by the ser function.
- by this way you can easily identifies the user , and execute their need.






