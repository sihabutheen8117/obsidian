- it intercept the req and res.

Example :
```
axios.interceptors.request.use(
	config =>{
		console.log(
			`${config.method} request send to ${config.url}`
		);
	return config;
	} ,
	error => {
		return Promise.reject(error);
	}
)
```

- it simply the method and url which is requested from the system.
- Pomise.reject(reason)  : This method is useful when you want to create a promise that fails intentionally, usually to simulate an error condition or to trigger error handling in asynchronous code.
- reason : This is the value with which the promise is rejected. It can be an `Error` object or any other value that you want to use to indicate why the promise was rejected.
#### Catch the rejected promises
```
rejectedPromise.catch(error => { console.log(error); // Output: 'An error occurred' });
```

- The `.catch()` method is used to handle the rejected promise and log the error to the console.