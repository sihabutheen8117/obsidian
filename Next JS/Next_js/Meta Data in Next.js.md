we can define metadata in next js 
- static meta data
- dynamic metadata

###### Note :
- if the meta data is defined in layout file that metadata will applied all the routes under it.
- if the meta data is defined in page file , that will applicable only in page file not entire children routes.
- if layout and it page also has the metadata means , the page meta data will be showed , it replace the layout metadata , note that **page metadata data will replace , not entirely delete the layout metadata. it means it replace the thing which not available in layout metadata , and which is changing in layout comparing page**
- simply combined. not replace.

#### Static metadata

```
export const metadata = {
	title = "it is my page title",
	description = ".........."
}
```
#### Dynamic Metadata

- it can change the metadata dynamically
```
export const generateMetadata = (params) => {
	return (
		title : `${params.id}`
	)
}
```

- params is the parameter of the page , url parameters.


### titles in Metadata

 - it is just define how the title will be set to the pages
 - consider we have two routes 
	 - app/               (parent layout)
	 - app/child       (pages)



app/
```
export const metadat = {
	title : {
		default : "it is default "
		template : "%s | my app"
	}
}
```

- default title will be set to it children which is not have it metadata.
- if we set the title in child page with title as "children" then the title will be set with the template for this the title of the child will be "children | my app"
- because it is the template will be applied to all the children

- if we dont want to use the template which is defined in the parent app/
app/child
```
export const metadata = {
	title : {
		absolute : "children"
	}
}
```

- here the title will be just children not children | my app , because he ignore parent using absolute.

