---
title: Sorting Algorithms (Part Two)
description: Sorting Algorithms explained to kids.
header: Selection Sort
duration: 2 minute read
layout: post
---

In my last post, i explained the [bubble sort algorithm](http://azu-n.com/2018/04/01/Sorting-algorithims.html). Today I
am going to talk about selection sort.

The selection sort is a similar algorithim to the bubble sort with slight difference. While boh algorithims
work by sequentially going through the list, the bubble sort as explained previously swaps elements if they
are not in the right place. Selection sort on the other hand scans the list looking for the largest 
element. After the first scan, if the largest number isn't at the end of the list, a swap occurs.

Lets take the list [54,26,93,17,77,31,44,55,20], we assume the first element (54) is the largest
item in the list. As we scan through, we compare each element of the list and if we find any element
greater than 54, we take note of its postition(index). At the end of the first scan, we swap the element
at the end of the list with the biggest item. We continue this process until the list is sorted.

So with the list above, we assume the element at positon 0 (54) is the largest element, we then compare
it with the item at positon 1(26). Since 54 is greater than 26 the largest element still remains at positon 0. We then compare this element with that at postion 2 i.e 54 vs 93 and this is larger so the larger element is now at postion 2.  We do this until we get to the end of the list and then swap the element at the
 end of the list with that of the largest element and reduce the size of the list by 1. 

 At the end of the first pass, the list would be [54,26,20,17,77,31,44,55,93].  We repeat the process again by
 <ol>
 <li> Pick the element as position 0 (54) as the largest item. </li>
 <li> Comparing the chosen element with others in the list starting from postion 1 to N-1. </li>
 <li> If we encounter an item greater than the chosen one, we the position of the greater one that of the max element. </li>
 <li> At the end of the pass, swap the element at N-1 with that of the largest item. </li>
 <li> Reduce N by 1. </li>
 </ol>





## CODE:

````


def selectionSort(alist):
    length = len(alist) - 1
    while length > 0: 
        maxPosition = 0
        for i in range(1, length + 1):
            if alist[i] > alist[maxPosition]:
                maxPosition = i
        temp = alist[length]
        alist[length] = alist[maxPosition]
        alist[maxPosition] = temp
        length -= 1

````

 