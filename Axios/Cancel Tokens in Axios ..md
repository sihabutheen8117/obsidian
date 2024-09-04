- it is used to cancel the request ,for some reasons

```
const source = axios.cancelToken.source();

axios.get('url?_limit=5 ,{
	cancelToken : source.token
})
	.then (res => {
		//res gives the response object
		console.log(res)
	}).catch(thrown => {
		if(axios.isCancel(thrown)){
			console.log('Request cancel',thrown.message)
		}
	}
	})
```


- it will run with out any error

after this if you add this or call this
```
if(true){
	source.cancel('Request Cancelled !')
}
```

OutPut : Request cancel Request cancelled !

Exaplanation :
- if you call this it will cancel the req, and throw a message which os source.cancel() doest.
- in the req section req will be canceled and catch will be executed thrown will be print the message which is thown when cancelling.
