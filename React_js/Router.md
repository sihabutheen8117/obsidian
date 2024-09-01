
### Why?
##### **Helps to navigate between urls**.
easily sharable with other users.
___

#### install react router from npm
```
npm install react-router-dom
```

---

#### import browser router

```
import {BrowserRouter} from 'react-router-dom'
```

it will allow to use all the feature in react router

---

packing

```
<BrowserRouter>
   <App/>
</BrowserRouter>
```

by doing this the app component can use the react router

----

### Route Configuration

#### importing routes and route
```
import {Routes ,Route} from 'react-router-dom'
```

**`Routes`** and **`Route`** are components that work together to define and manage the navigation structure of your application

##### Routes
**`Routes`** is a component that replaces the older **`Switch`** component from React Router v5. It is used to group multiple `Route` components and render the first one that matches the current URL.

##### Route
**`Route`** is a component that defines a mapping between a URL path and a component. When the current URL matches the `path` specified in a `Route`, the component defined by `element` or `component` is rendered.

props of Route
- **`path`**: Defines the URL pattern to match.
- **`element`**: Specifies the JSX element to render when the path matches. (This replaces the `component` prop from React Router v5).
- **`exact`** (React Router v5 only): Ensures that the path matches exactly. In React Router v6, exact matching is the default behavior, so this prop is no longer needed.

#### Example ( this code is under the app component)
```
<Routes>
	<Route path='/' element={ <Home/> } />
	<Route path='about' element={ <About/> } />
	
</Routes>
```

'/' -> Means the root of the react app which is mostly port 3500

when you visit about it will shows the <About/> component

---

### link

##### inport link component
```
import { Link } from 'react-router-dom'
```

link- it is used to navigate from one route to another route

Example 
```
<Link to='/page'>About<Link/>
```


#### NavLink

##### What is navlink ?
- it is just a link with predefined or applied css class called active
- we can change the css class active

###### import navlink component
```
import { NavLink } from 'react-router-dom'
```

- simply we can put NavLink instead of Link for using NavLink component

##### Style props for navlink
- navlink has a props called style
```
<NavLink style={function} to='/page'>About<NavLink/>
```
in that function
```
	const function = ({isActive}) => {
	return(
		you code here
		example
			retune the css styles 
			example
				fontWeight : isActive ? 'bold' : 'normal' ;
	)
	}
```

isActive - reurns the link is active or not. whether i am currently this route or not .

---
### Navigate programatically

##### what does it mean ?
- when you wants to navigate a page , when an event occure for example when you click this button you should go to the about page.

#### How?
- for this you shouls import the useNavigate component from react router dom
- call this funtion when event occure with argument about page

#### Example:
###### importing
```
import {useNavigate} from 'react-router-dom'
```

###### logic
```
const navigate = useNavigate()
return(
	<button onClick{()=>navigate( 'about' , {replace : true} )}> Go to About <button/>
)
```

###### Exaplanation
when you click this button it will call navigate funtion with the about argument ,
then about page will display 

###### ok what is replace : true
this is optional argument when about home page loded , then you create a button then name as go back for that navigate funtion put -1 as a argument (instead of about) , then if you click it will go all the way back (it means completly exit of that website)
if you dont use it just return the page here home page beacuse home/about.

----
### Configure no match routes

simply but * for the path , it will show when no path matches.

##### Example
```
some other routes
<Route path='*' element={<404 not fount/>} />
```
if no one matches it will return <404 not fount />

---
### Nested Router in React

#### Why?
you know why , when the route return to another navigations (routes) then it need nested route.

#### !important
##### Example
```
<Route path='/product' element={<Product/>}>
	<Route path='/old' element={<Old/>} />
	<Route path='/new' element={<New/>} />
</Route>
```

###### Note
- here we are using not self close route (product)
- beacuse we should pass the childrent old and new to the product

###### Product component
import outlet
```
import {Outlet} from 'react-router-dom'
```
Why?
- it has the capanbility to show the childrent component
- link only link the component 

```
<link to='old'>Old<Link/>
<link to='new'>Old<Link/>
<Outlet/>
```

the link component link the childrent , and outlet shows the component which is matched or linked to that component

Note:
- we did not provide product/new because react automatically add the product before new
- how ? 
- because it is children of the product , we specified

-----
### Index Route

#### What is it ? Why we need?
- in the above example you saw that whenever you go to the prduct you will see new and old link
- but new and old component content will not shown ,when click that it will show.
- but *__we want to show the old product when you enter product . that means before you click old or new component

Example:
```
<Route path='/product' element={<Product/>}>
	<Route path='/old' element={<Old/>} />
	<Route path='/new' element={<New/>} />
	<Route index element={<new/>} />
</Route>
```
here i put index as new when you go product it automatically shows the new component

----
### Dynamic Route

Example:
```
<Route path='user/:id' element={<UserId/>} />
```

it will return UserId Component When you visit user/id
- for id you can put anything 1,2,a,b,c, and so on,

----
### URL Params

#### params - parameters

see the above example when you wants to extract the id value in the UserId Component we should use useParams hooks

import
```
import {useParams} from 'react-router-dom'
```

logic (UserId component)
```
const params = useParams()
console.log(params.id)
```

it will return the id example 1,2,3,a,b, and so on ,you know

----
### Search Params

you can give the optional query string for example
- localhost:3000/user/id?filter=true

we need search param hooks
```
import {useSearchParams } from 'react-router-dom'
```
this hook has
```
const [seacrhParams ,setSearchParams ] =useSearchParams();
```
- searchParams return object;
- setSearchParams returns function;

```
	<button onClick={ () => {setSearchParams ({filter : 'active'}) } }> Active <button/>
```

Getting the params 
```
	const check = searchParams.get('filter')
```

----
## Relative links

it does not start with the / it will inherit the parent or nearest path 
for this example see the nested route in the above we have wrote.

if you put / before old or new it does not shows the page because it will construct from the route not a parent 

-----

### Lazy Loading

- when your website have so much files and size in bigger then the initital load it takes will be more 
- to reduce that we use technique called lazy loading 
##### How it is works
- define the any component you wants to load after click.
- first time you enter the website it loads the all the component , except one you defined lazy loading 
- if you go that component then only it will load , and cached.

export the component default
```
export default About
```

then we should import about page dynamatically
 for this we need 
 ```
 import React from 'react';
 const lazyabout = React.lazy( () => import('./component/about'))
```

in the app function
```
return(
	<Routes>
		<Route path='about' element={
			<React.Suspense fallback='loading...'>
				<Lazyabout />
			<React.Suspense />
		} />
	<Routes>
)
```

- fallback - when it is loading it will display loading...
- suspense - allows you to wait for some code or data to load before rendering a component. It's especially useful when you're working with asynchronous operations, like fetching data from an API or loading a component lazily
-----
### Authentication with React Router

- used to prevent the user to visit the page without logged in
- 
