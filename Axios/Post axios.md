

- want to see the express post api handling -> [[POST req in Express]]


### Example:
```
axios({
	method : 'post',
	url : 'url' //basically a backend url ,what you want to get.
	data : {
		//put the data you want to send to the server
	}
	}).then (res => {
		//res gives the response object
		console.log(res)
	}).catch(err => {
		 //error handling part
		 console.log(err)
	})
```

data : your data ,need to send to the server.