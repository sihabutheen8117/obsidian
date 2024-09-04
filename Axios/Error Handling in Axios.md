Example :
```
axios.get('url?_limit : 5 )
	.then (res => {
		//res gives the response object
		console.log(res)
	}).catch(err => {
		 if(err.response){
			 //Server responded with a ststus other than 200 range
			 console.log(err.response.data);
			 console.log(err.response.status);
			 console.log(err.response.headers);
		 }
		 else if(err.request){
			 //request was made but no response
			 console.log(err.request);
		 }else{
			 //other than that.
			 console.log(err.message;
		 }
	})
```

it is simply handling the error with the conditions.

-----
##### Validation
- put this as a property of the method , example after the url

```
{
	validateStatus : function(status) {
		// it will only throw the error when the return status code is greater than 500 ,even 404
		return status < 500 ;
	}
}
```

- we should tell or return a boolean ,which will be like whether throw the status code error or not. 