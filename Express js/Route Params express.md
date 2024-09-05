
in client side after the pages , include the whatever you want after the '/' it will be consider as params

params - parameters

```
app.get('/ : id ' ,(req ,res)=>{
	console.log(req.params)
})
```
output : 
```
{id : 'your entered number after /'}
```

we can also get the id directly like this (not an object)
```
//inside the app.get

console.log(req.params.id)
```
return value of the id will be string , we need to parse the string
use parseInt() function to convert them.




