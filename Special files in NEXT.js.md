

- page and layout also a special file in next

#### non-found
- to modify page 404 not found.
- if you not create it next already does it for you.
#### Template

- template is same as layout.
- what layout does is it share the component or DOM element across it child ,that means when you create a element in template it is applicable for all the child element of the template.
- that means all child element can see the element , which is created in layout.
- but in template. if you create a dom element in template ,it is also visible for their childs.
- lets take you are created a element m1 in template.
- when you navigate template child 1 , you can see m1.
- if you navigate template child 2 ,you can also see m1 but it is not that m1 it is newly created m1 for child 2 only . 
- if you change the m1 in child2 ,child2 only seee the changes , not entire childs.


for create a template file just name it as **template.tsx** or **template.js**

#### Loading
- loading is used to show the element is loading you can modify it.


#### error
- must be client component (for working )
- to show the error message.
- if you create a error file all other works except error element.

- how handle the error in client side.
- we can add the reset button to rerender the component in client side.
- for that. in error file. we get reset function as the props ( dont worry , simply put reset in the argument as props )
- and use it when props invoked the component will be rerendered.



