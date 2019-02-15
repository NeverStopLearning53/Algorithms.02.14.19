# **Exercises**
## **Submit answers to the following questions:**

#### **1. Out of the sorting algorithms introduced, or any others you have encountered, which is the quickest or most efficient in sorting a set of data and why?**

Great question ... my short answer would be ... "It depends" ... 

There is a trade off between speed and amount of memory an algorithm will use. Generally the faster the speed of an algorithm the more memory it will take to run.


If your data set contains integers than Radix Sort would be my preferred sorting method.

QuickSort is great for generalized sorting, if …
* Your input sets are generally random.
* Your entire data set fits into memory. 
* You don't need it to be stable.
* You don't need it to adapt to already or mostly-sorted inputs.

If the data is mostly-sorted, then Insertion or Shell can be great.

If you really must eliminate the possibility of that worst-case scenario, you could use Heap sort.

Merge is a great stable sort but it is a memory hungry algorithm. It is also the only real choice if the data set is too large to fit into memory.

#### **2. Why is Binary Search more efficient than Linear Search for most cases?**

First and very important Binary searches **only** work on sorted arrays.
Binary Search is advantageous over a standard Linear Search because it search faster and more efficiently due to what some developers call as “Dividing and Conquering.”

Instead of searching an array at index 0, 1, 2, 3, 4, and so on like we do in a For Loop, Binary Search allows us to divide our search in half each time we look for a target value. We define a middleIndex or midpoint from the element in the middle of the array (Divide) to see if our target value is greater than or less than the middleIndex or midpoint. Depending on if the target value is greater than or less than the middleIndex, we can remove the left or right of our array from our search (Conquer).

#### **3. Code an implementation of Bubble Sort and test it on an integer array of your choice.**

```
function bubble_Sort(listofNumbers) {
    
  var swapp;
  var n = listofNumbers.length-1;
  do {
     swapp = false;
     for (var i=0; i < n; i++)
 //Using a for loop it starts with i = 0 then keeps running (adding 1 to i each loop until i < (the length of the array - 1) )         
     {
         if (listofNumbers[i] < listofNumbers[i+1]) //if listofNumbers[i] is less than listofNumbers[i+1] then execute this block of code
         {
            var temp = listofNumbers[i];
            listofNumbers[i] = listofNumbers[i+1];
            listofNumbers[i+1] = temp;
            swapp = true;
          }
     }
     n--; // decrement n by 1
    } while (swapp); // the while executes thru a block of code as long as the specified condition is true
  return listofNumbers; 
}

console.log(bubble_Sort([12, 345, 4, 546, 122, 84, 98, 64, 9, 1, 3223, 455, 23, 234, 213]))
```


