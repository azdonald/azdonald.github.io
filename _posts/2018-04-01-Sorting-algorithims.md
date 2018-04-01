---
title: Sorting Algorithms (Part One)
description: Sorting Algorithms explained to kids.
header: Bubble Sort
duration: 4 minute read
layout: post
---

One of the most common and important tasks in computing is sorting. It's so common that every programming language comes with at least one sorting function. Over time, we get so accustomed to using the built in functions, we forget how they work. This is especially true for self taught developers.

In this series, I am going to try and explain the different sorting functions available in the simplest way possible. You would and should not have to write your own sorting function, but knowing how they work is nice.

For this post, we are going to be looking at the bubble sort.


The bubble sort is probably the simplest sorting algorithm and its works by going through a list/array and swapping adjacent elements if they are not in the right place. Understanding this line is the key to understanding the bubble sort and I would be using a list to explain this further.

Given the list [8,6,4,5,2], the bubble sort algorithm would take the first two elements i.e 8, 6 and compare them. Since 8 is greater than 6, we swap them.
So the list becomes [6,8,4,5,2]. We now move on to the next two elements 8,4 and do the comparison again and since 8 is greater than 4, another swap is performed. The 
list now becomes [6,4,8,5,2]. Next is 8, 5 and as we know, 5 is less than 8 we swap and the 
list becomes [6,4,5,8,2]. We now compare the final two items 8, 2. With 8 being greater than 2, we swap them so the list becomes [6,4,5,2,8]. We've gotten to the end of the list but the list is not sorted, so we start from the first two elements and go all through the process of comparing each adjacent elements until we sort the list.  

6,4 => [4,6,5,2,8]  
6,5 => [4,5,6,2,8]  
6,2 => [4,5,2,6,8]  
6,8 => [4,5,2,6,8]  
4,5 => [4,5,2,6,8]  
5,2 => [4,2,5,6,8]  
5,6 => [4,2,5,6,8]  
6,8 => [4,2,5,6,8]  
4,2 => [2,4,5,6,8]  
4,5 => [2,4,5,6,8]  
5,6 => [2,4,5,6,8]  
6,8 => [2,4,5,6,8]  


One thing to note is on each pass, the largest elements are moved to the back of the list while the smaller elements bubble to the front.

## CODE:

````

def bubbleSort(aList):  
    noOfItems = len(aList) - 1  
    while noOfItems > 0:  
        for i in range(len(aList) - 1):  
            if aList[i] > aList[i + 1]:  
                temp = aList[i]  
                aList[i] = aList[i + 1]  
                aList[i + 1] = temp  
        noOfItems = noOfItems - 1
        
````
Its is important to note that the bubble sort is not an efficient sorting algorithm, especially when the list is large.


PS: Python allows for the direct swapping of elements so rather than use a temp variable I could have done  
aList[i], aList[i + 1] = aList[i + 1], aList[i]  
I chose to use the temp variable for the benefit of none python developers.
                
  