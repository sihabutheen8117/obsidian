- it is simply used to create a custom headers for the req , res methods
- Example : when you wants to auth the user credentials using the tokens in the backend side we can make the req with header consists of the user token.

#### Example
```
const config = {
	headers : {
		'Content-Type' : 'application/json',
		Authorization : 'someToken'
		}
};

axios({
	method : 'post',
	url : 'url' //basically a backend url ,what you want to get.
	data : {
		//put the data you want to send to the server
	} ,
	config
	}).then (res => {
		//res gives the response object
		console.log(res)
	}).catch(err => {
		 //error handling part
		 console.log(err)
	})
```

- config will be the parameter of the post function
- in the config contend type and authorization is defined by us. we can put anything we want.
