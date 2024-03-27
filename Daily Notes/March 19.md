# Data Structures
**March 19, 2024**

## Arrays vs. Lists
Arrays store a group of variables sequentially in memory.

When a new variable is added, two things can happen:
* The memory after the array is free:
  * The variable is added to this memory
* The memory after the array is occupied:
  * The **entire array** is copied from its original location to a new location that can hold the array + the new variable.

This second case is not ideal!

Instead, a "list" can be used.

Lists store data nonsequentially in free memory, which makes it much easier to add or remove elements of the array.
* Each element in the list contains the data it is storing itself followed by the memory address of the next element. (This type of list is called a "linked list".)
* This allows each element to be in any arbitrary memory location.

### Benefits of Linked Lists:
Adding or removing elements is simple.
* Addition: Allocate element, then change the address of last element to point to the new element.
* Removal: Change address of element before element to remove to the element ahead of the one being removed, then deallocate the element.

### Benefits of Arrays:
The address of any array element can be calculated since all array elements are the same size and stored sequentially.
* `memory address of the start of the array + element size * index of desired element`
* This means that accessing any element has a fixed cost.
* Compare this to a list, which requires the program to traverse every element before the desired one to find it.