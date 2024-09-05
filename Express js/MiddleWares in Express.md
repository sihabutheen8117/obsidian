
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

- we should register the middle ware in express by use method.
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
#### 
