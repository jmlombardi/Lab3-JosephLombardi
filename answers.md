#####Joseph Lombardi
#####COMP 271: Data Structures
#####Lab 3
#####Due 06/20/2018
[Click here for My GitHub Lab 3 Repository](https://github.com/jmlombardi/Lab3-JosephLombardi)

#TestList.java Questions
1. TODO also try with a LinkedList - does it make any difference?

    Using a LinkedList vs. using an ArrayList in this lab doesn't make a difference. One of the big advantages of using a LinkedList is that you can insert an element at the beginning of the list in constant time(O(1)).  Also a LinkedList doesn't have to double its size when it reaches max capacity and vice versa when removing elements. If you loop through either list then your time complexity is going to be O(n).  In our lab our lists never reach a size greater than 7 elements so the ArrayList seems to be just as efficient as the LinkedList.  When I ran the 12 cases for each list I received the same results for both the LinkedList and the ArrayList.

2.  list.remove(Integer.valueOf(5)); // what does this one do?

    The remove() is overloaded and can an int index or an object.  For this specific question we are passing it an an object of type Integer and calling the valueOf() which Returns an Integer instance representing the specified int value. The remove() then removes the value five from list.

#TestIterator.java Questions
1. TODO also try with a LinkedList - does it make any difference?

    My findings were the same as question 1 for TestList.java.  Using a LinkedList vs. using an ArrayList in this lab doesn't make a difference.  Please refer to that answer.

2. TODO what happens if you use list.remove(Integer.valueOf(77))?

       The remove() is overloaded and you can pass it either an index of type int or an object. In our case we are passing it object type of Integer as a representation of int 77.  This method returns a boolean.  If the value you are passing to the remove() is present in your list it will only remove the first occurence of that value.  Creating an Iterator and using the while loop I ran my test 3 times and my results were 2ms, 3ms and 2ms.  When I used list.remove(Integer.valueOf(77)) I ran my test twice and both times my results were 3ms.  It seems that creating an Iterator is more effecient.  As you mentioned using list.remove(Integer.valueOf(77)) has to create an Iterator in the background.  My findings are creating an Iterator and removing all three values of 77 is more effecient then using list.remove(Integer.valueOf(77)) to remove one element.

       


#TestList.java Questions

1. Which of the two lists performs better as the size increases?



    testArrayListAccess() - Returns the element at the specified position in this list.

    testLinkedListAddRemove() - Inserts the specified element at the specified position in this list THEN Removes the element at the specified position in this list.

    testLinkedListAccess() - Returns the element at the specified position in this list.

    testArraylistAddRemove() - Inserts the specified element at the specified position in this list THEN Removes the element at the specified position in this list.

In conclusion to my test results you can clearly see that it takes significantly longer to access elements in a LinkedList vs an ArrayList.  ArrayLists have O(1) for random access because you are accessing an index directly.  On the other hand ArrayLists are very expensive to add or remove because you have to shift all of the elements which is O(n).  This also may include increasing the size of the ArrayList which would create a new array in the background and copy all of the elements to the new list.  If you add an element to the end of an ArrayList that would be O(1) assuming you are not at full capacity.  LinkedLists are much quicker than an ArrayList when adding an element at a specified position and or removing because you are just updating reference pointers.  LinkedLists are O(n) for random access because you always have to start at the head and loop through.





    |                 size(n) | 10s  | 100  | 1,000 | 10,000   | 100,000   | 1,000,000     |
    |------------------------:|------|------|-------|----------|-----------|---------------|
    | testArrayListAccess     | 11ms | 14ms | 12ms  | 18ms     | 32ms      | 253ms         |
    | testLinkedListAddRemove | 48ms | 36ms | 38ms  | 42ms     | 68ms      | 344ms         |
    | testLinkedListAccess    | 12ms | 33ms | 371ms | 4s 113ms | 43s 931ms | 21m 19s 462ms |
    | testArraylistAddRemove  | 83ms | 82ms | 192ms | 1s 303ms | 18s 533ms | 6m 10s 115ms  |