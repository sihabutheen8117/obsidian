
- data validation in the server is very importand.
- both client and server should be validate the data.
- here your actually stores the data in database so server side validation is very importand.

- here we are using the predefined express validator.
- it contains many methods you can use it for validating (example ,isString() ,...)

##### Installing express validator.
```
npm i express-validator
```

##### importing

- query validator.
```
import {query } from 'express-validator'
```

- you validate the data incomming query using query validator by the chain of validation for exmple , if you wants to validate the query.
	- add the query() function as a middleware
	- give the query as a function argument Ex.query("filter");
	- add your pre defined validator like a chain . ex.query("filter").isString().and go on.
	- this will not thrown an error if condition failed ,it simply reject.
	- this query middleware attach the errors in "express-validator#contexts" with the request object , so that we can see the error details in by request object.

- another method to see the the errors in another middleware is ,you can use validationResult function. first we should import that.

import validationresult to see the errors
```
import {validationResult} from 'express-validator'

```

using validatorResult in another middle ware.
```
const result  = validationResult(request);
console.log(result);

```
it will return the array of object.


how to check which error is which.
- validationREsult will return the object that tells us it is error.
- but we use many validation we dont know which error message is for which validation.

For this we can do.
```
Query().isString().withMessage("value must be string")
```
- set this after every validation example .isStrign().withMessage("value must be string");


#### Validation of Req body
```
import {body } from 'express-validator';
```

add body() insteaad of query().
- inside the body(here) put ,what you wants to validate example username ,which is came from the client body object.
















