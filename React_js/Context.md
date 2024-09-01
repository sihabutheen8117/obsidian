
### Why we need this ?
Consider we have 4 component A ,B ,C ,D
A component return B , B return C ,C return D
- if you want to send the data to A to D you use prop drilling that means A to B to C to D
- for alternative this we can use context

create a context in usercontext component
```
import React from 'react'
const userContext = React.createContext()
```

it comes with provider and consumer (usercontext)

```
const userProvider = UserContext.Provider
const userConsumer = userContext.Consumer
```

now we should decide the which component is provider
in our app A is privider
- import the userProvider from userContext
in A component
```
<userProvider value="Passing value">
<B />
<userProvider/>
```

choose consumer 
in our app D is consumer
- import the userConsumer from userContext
in D component
```
<userConsumer>
{
	(value)=>console.log(value);
}
<userConsumer />
```
- in this code the consumer child have the value which is passed from the A
- so we get the value and print in the console

----
### set default value

```
import React from 'react'
const userContext = React.createContext('passing value')
```
- from this method u can set the default value.
