---
title: Sorting Algorithms (Part Three)
description: Sorting Algorithms explained to kids.
header: Insertion Sort
duration: 2 minute read
layout: post
---

Today post is going to explain the insertion sort. The insertion sort like the two previous sorting algorithms we talked about is a sequential algorithm. So how does it work you may ask, well that's what the post is for. 

The insertion sort works by maintaining two lists and making sure that at every point in time, one of the list is always sorted. So how is this different from the bubble sort and the slection sort you may ask, well lets explain this with an example.

Given the list [54,26,93,17,77,31,44,55,20], the insertion sort algorithm assumes that the first element (54) is a list on its own and it is sorted. The algorithm now scans the second list (from  26) and compares it with the items in the sorted list and puts the element in the right place.

In our example list, we know list one contains the item 54 and its sorted. List 2 contains 26,93,17,77,31,44,55,20 and we don't care about it order. On the first pass, we take 26 and compare it with the items in list one to find its right place and thats before 54 so list one becomes [26, 54] while list two has [93,17,77,31,44,55,20]. Our next part sees us taking the item 93 and comparing it with list one. Since 93 is bigger than the biggest element in list one, we know its right full place is at the back of the list so list one becomes [26, 54, 93].

We continue like this until the list is completely sorted. The difference between this and the previous two we discussed is that in the bubble sort, we compare two adjacent elements and swap as necessary; the selection sort scans  for the largest element and moves it to the back of the list while this one works by always maintaing a sorted list(initally the first element) and continues to add other elements to their rightful place in each scan.



## CODE:

````


def insertionSort(alist):
    for i in range(1, len(alist)):
        position = i
        while position > 0 and alist[position - 1] > alist[position]:
            temp = alist[position - 1]
            alist[position -1] = alist[position]
            alist[position] = temp
            position -= 1

````