
- generally middle ware is the process between the main other processes.
- for in express it is the function which is run between the req catch from the server (app.get or something) and response.
- in express the middle has the 3 arguments which is reqest ,response and next() function.
- next function is used to call the other next middlewares or end code that is response code.
- call next when you are done with the middleware .

we can define the middle ware in two types 
1.global middleware.
2.with in the methods (app.get somthing like methods)

----
#### 1.Global middleware.

- we should register the middle ware in express by use method. (use used to register globally , means for all the things)
- and define the middleware.

```
//define the middleware
const loggin = (req ,res ,next) = {
	console.log(`${req.method} - ${req.url}`);
	next() ;
}

//register the middleware
app.use(loggin);

```

- it will be enable globally so no need to pass the middleware.
- any function (like app.get()) executed , middleware automatically called.

----
#### 2.With in the methods

it will be called only if that function is called

```
const loggin = (req ,res ,next) = {
	console.log(`${req.method} - ${req.url}`);
	next() ;
}

app.get('url' , loggin , (req ,res)=>{})
```


----

- next is option you called or prevent to call next .
- next gives us control to call the next middleware.


#### How to pass the data from one to middleware to another middleware ?

- we are using javascript it dynamically ,add the properties into the object.
- by this feature we can attach the processed data with the request ,in next middel we can get that data from the request object.

Example ;
```

const firstmiddleware = (req, res ,next) => {
	const firstmiddlewareData = "first middle ware"
	req.firstmiddlewareData = firstmiddlewareData;
	next();
}

const secondmiddleware = (req ,res ,next) =. {

	console.log( req.firstmiddlewareData );
	next();
}


app.get('url' ,  firstmiddleware , secondmiddleware, (req ,res)=>{})


```

we attached the firstmiddleware in the req object.
and we access the firstmiddleware by the req in secondmiddleware

