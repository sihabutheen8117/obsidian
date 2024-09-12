
#### Installing bcrypt
```
npm -i bcrypt
```

- do this another file (example : helper)

```
import bcrypt from 'bcrypt'

const saltRound  = 10;

export const hash = (password) => {

	const salt = bcrypt.genSaltSync(saltRound);
	return bcrypt.hashSync(password ,salt)

} 

```

- saltRound  : it means how much the password should strong enough , increase this will increase the complexity of the password and time to calculate and retrive the password.

### how to compare the password with the hashed  password.
```
	const auth = bcrypt.compareSync( password , hashedpassword )
```

it will return true if it is same else false.