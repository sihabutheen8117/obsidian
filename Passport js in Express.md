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

- import this file in 
- it is the stradegy for ur authendication.
- if u wants to use email as a username which is came from the client side just use username filed and out whatever u want email something like that (it will take email from the req body as a username) , or u want to use username as username just leave it that .
- Done function : 
