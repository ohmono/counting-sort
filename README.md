> ##### *-Juan Cardona* 

Explanation of counting sort functionality and demonstration of their lineal magnitude order.

Counting sorts is a special sorting algorithm that runs in linear time with respect to two variables: 
- $n = len(array)$ 
- $k = maxValue - minValue + 1$ 
- $O(n+k)$

---
It is a sorting algorithm where we know something about the input, they are all positive integers. 
Counting sort assumes that each element in a $arr$ has a value ranging from $minValue$ to $maxValue$, with $(minValue, maxValue) \epsilon  \Z$. 

- $arr$
- $minValue$
- $maxValue$

For each element in the list, counting sort determines the number of elements that are less than it. Counting sort can use this information to place the element directly into the correct slot of the output array.

Counting sort uses three lists: 
- A the input list, $arr=[3, 8, \dots, minValue, 34, 6, \dots,maxValue]$
- B the output list, $solution=[0,0,0, \dots, n]$
- C temporary memory list, $counter=[0,0,0, \dots, k]$
  - $n=len(arr)=len(solution)$
  - $k=len(counter)=maxValue-minValue+1$

---
Counting sort starts by going through $arr$, and for each element $arr[i]$, it goes to the index of $counter$ that has the same value as $arr[i]$ (so it goes to $counter[arr[i]]$) and increments the value of $counter[arr[i]]$ by one. 

---
Next, modify $counter$ so that each $counter[i]$ includes the number of elements less than it. This can be accomplished by going through $counter$ and replacing each $counter[i]$ value with $counter[i] + counter[i-1]$. This step allows counting sort to determine at what index in $solution$ an element should be placed.

---
Then, starting at the end of $arr$, add elements to $solution$ by checking the value of $arr[i]$, going to $counter[arr[i]]$, writing the value of the element at $arr[i]$ to $solution[counter[arr[i]]]$. Finally, decrement the value of $counter[A[i]]$ by $1$ since that slot in $solution$ is now occupied.

!["counting sort rexamlpe"](https://d18l82el6cdm1i.cloudfront.net/uploads/hrUDdYC7OH-countingsort.gif) 

## References

- ['Counting Sort: An Exploration of Sorting Special Input In Linear Time'](https://www.youtube.com/watch?v=1mh2vilbZMg)
- ['Counting Sort](https://brilliant.org/wiki/counting-sort/#:~:text=Counting%20sort%20is%20an%20efficient,to%20them%20by%20some%20scheme)