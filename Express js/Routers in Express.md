
more about react router (client) -> [[Router]]

note that route or router means
something like app.get() ,app.post like that you know;

what is router
- router is like a seperate express ,what ? not exact ,like that.
- we can define routes or apis in another file and import in express main server file to relive from confusion


#### How to do that.

we have 2 file one is server.js , another is user.js
- why user.js means it will contain all user domain routes , domain means locations or which we mentioned after app.get( '/here ' , () );
- by that we can create n number of files for any domains.

in user.js
```
import {Router} from "express";

const router = Router();

router.get()
//something what we done in express.


export default router;
```

in server.js
```
import express from "express"

import router from "/folder location"

const app = express();

app.user(router)
```
- use user.js router we must register in express using app.use()
