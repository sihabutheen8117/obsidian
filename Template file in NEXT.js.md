
- template is same as layout.
- what layout does is it share the component or DOM element across it child ,that means when you create a element in template it is applicable for all the child element of the template.
- that means all child element can see the element , which is created in layout.
- but in template. if you create a dom element in template ,it is also visible for their childs.
- lets take you are created a element m1 in template.
- when you navigate template child 1 , you can see m1.
- if you navigate template child 2 ,you can also see m1 but it is not that m1 it is newly created m1 for child 2 only . 
- if you change the m1 in child2 ,child2 only seee the changes , not entire childs.


for create a template file just name it as **template.tsx** or **template.js**

