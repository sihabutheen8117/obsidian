
- put req used to update data.
- put update the data means , it entirly replace the data . (existing data)
- patch req update portion of the data not entire data.
- more about client put / patch req -> [[PUT or PATCH Axios]]

EXample : 

```
app.put('url/:id' (req,res)=>{
	const {id} = req.params;
})
```
