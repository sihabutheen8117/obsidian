#### local modules

we created during developement
any file youhave created
it is isolated by default

##### importing
```
require{"/your file"};

```
it add the module
it atomatically append the file and run this.

-------

##### Exporting
```
module.exports = your function or variable son on.
```

-----

##### Imitiatly running functions
```
(function() {
	console.log("it will runautomatically")
}) ();
```

all the module wrap in this funtion(iife) before it loaded

------

