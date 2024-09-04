- it will create a predefined base method which is added to the req when req created.
```
const axiosInstance = axios.create({
	//Other custom settings
	baseURL : 'baseurl'
})


//this will req with the baseurl+url
axiosInstance.get('url').then(res => showOutput(res));

```