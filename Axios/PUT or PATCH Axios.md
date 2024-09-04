- PUT and PATCH are used to update the data
- put : replaces the entire
- patch : part of that.
- in ure we should specify the id also see the url

##### PUT
```
axios({
	method : 'put',
	url : 'url/id' //basically a backend url ,what you want to get.
	data : {
		//new data for id
	}
	}).then (res => {
		//res gives the response object
		console.log(res)
	}).catch(err => {
		 //error handling part
		 console.log(err)
	})
```

id : put the id which need to update entirely
- it return res as the updated value
- mind it , it replace the entire object with that you specifued in the data section, other value of the onject will be deleted.

### PATCH
- same as the put method but it change the values we mentioned in the data section. and other values of that object remain same 
