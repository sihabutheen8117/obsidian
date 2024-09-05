
looking for client get req => [[Get Axios]]

```
app.get("/" ,(req ,res) => {
	res.send(Whatever you want to send)
	//or json object
	res.send({
		name : express 
	})
})
```

req - from client 
res - to client
"/" - client requested page

set the status code

```
app.get("/" ,(req ,res) => {
	res.send(Whatever you want to send)
	//or json object
	res.status(201).send({
		msg : "Express"
	})
})
```

default status code is -> 200 ,success code

