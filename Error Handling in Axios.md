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