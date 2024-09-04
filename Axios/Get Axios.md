#### Example :
```
axios({
	method : 'get',
	url : 'url' //basically a backend url ,what you want to get.
	params : {
		_limit : 5 _
	}
	}).then (res => {
		//res gives the response object
		console.log(res)
	}).catch(err => {
		 //error handling part
		 console.log(err)
	})
```

- here the url refers to the backend url , that returns the json data onjects.
- res not return actual data ,res.data return the actual data
- in params -> limit is used to limit the receiving data , here we limits 5 object 

#### Or (works same as before)
```
axios.get('url' ,{params : _limit : 5 })
	.then (res => {
		//res gives the response object
		console.log(res)
	}).catch(err => {
		 //error handling part
		 console.log(err)
	})
```

#### Or(works same as before)
```
axios.get('url?_limit=5 )
	.then (res => {
		//res gives the response object
		console.log(res)
	}).catch(err => {
		 //error handling part
		 console.log(err)
	})

```

- we can omit get (defaults is get)

