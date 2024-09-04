```
axios.all([
	axios.get('url'),
	axios.get('url')
]).then(res=>{
	console.log(res[0]);
	console.log(res[1]);
	showOutput(res[1]);
}).catch(err => console.log(err));
```

### Or
```
axios.all([
	axios.get('url'),
	axios.get('url')
]).then(
	axios.spread((res1  res2) => {
		showOutput(res1);
	})
).catch(err => console.log(err));
```

- spread : it used to specifing the name of the response instead of using res[1] or res[0] .