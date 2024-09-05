
- carry data from client to server then saved in server.
- when client to need to stores the data in server , which is get from the client.
- the data called req body. or payload.
- more about client post req -> [[Post axios]]


{Note : user data validation should be done both client and server side , it is good practice}

- for fake client in vsCode install -> thunder client
	- it is allows to create a client side api and req.


Example :

server
```
app.post('url' ,(req,res)=>{
	console.body(req.body);
})
```
output : undefined.
because.
- express will not parse that body
- for getting data we should create middleware

we want to send the json file from client to server.
so that include the below code in express.
- it will allow to parse the json automatically
```
app.use(express.json());
```



