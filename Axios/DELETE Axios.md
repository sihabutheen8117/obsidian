
- want to see the server (express ) delete handling api -> [[DELETE req in express.]]

```
axios({
	method : 'delete',
	url : 'url/id' //basically a backend url ,what you want to get.
	}).then (res => {
		//res gives the response object
		console.log(res)
	}).catch(err => {
		 //error handling part
		 console.log(err)
	})
```

- id : what object you want to delete
- it will return empty object



