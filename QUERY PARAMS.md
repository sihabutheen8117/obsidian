
- it is like a route params
- but it is start with '?' symbol.
- if you want to more query add '&' between them.
- it is not added in request body.
- it is added in url like hute params.
like
	http://url?filter=express

Example:

```
app.get('url' ,(req ,res)=>{
console.log(req.query)
})
```

Output :
```
{ filter ; 'express'}
```
return value will be json




