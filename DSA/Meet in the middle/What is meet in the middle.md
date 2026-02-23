There is given integer array and the number A
When you want to find the sum of element in an array so that it will nearest to A
You need to find the sum alone not array elements 

[1,2,7,4]  and A=10
Ans -> 9 from [2 ,7 ]

### How its Works

1.divides the array in to 2 parts in the middles 
[1,2] and [7,4]

2.find the all posible sum for the both arrys 
[0,2,7,9] and [0,7,4,11]

3.sort the second array
 [0,2,7,9] and [0,4,7,11]

4.assign i pointer to first array and j pointer to second array

5.for every i pointer move j pointer and sum those to get the value and stores the nearest value 

For searching in j apply binary search because it js sorted 

[0,2,7,9] and [0,7,4,11]
 i.                     J
