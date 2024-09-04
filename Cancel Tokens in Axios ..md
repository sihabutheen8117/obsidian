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

}
```