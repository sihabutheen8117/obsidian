
- cookies are small amount of data ,which is webserver send to the client browser.
- client web browser then stores that cookies.
- refreshing cant delete the cookie.

you can send the through response object
```
	response.cookie("name of the cookie" ,"value of the cookie" , { maxAge : 10 //ms})
```

maxAge is the life of a cookie in client side , after this time the cookie will expires.

how to get the sended cookie,
```
const cookie = request.headers.cookie
```

it will return unParsed cookie ,that is string ,we cant do anything with that so ,we need to parse that cookie ,
we can use third party to parse that cookie or we do manually ,

third party cookie parser from npm (installing)
```
npm -i cookie-parser
```
cookie-parser also a middleware in express pov.

import cookieParser from cookie-parser;

```
app.use(cookieParser())
```

after this if you log cookie from client
```
console.log( request.cookies )
```
it will return a object like { name : "value"}


