- it simply tells how to get the res , which means i should get res data uppercse like that

```
transformResponse : axios.defaults.transormResponse.concat(data =>{
	data.title = data.title.toUpperCase();
	return data;
})
```
- add this as a new argument of axios function