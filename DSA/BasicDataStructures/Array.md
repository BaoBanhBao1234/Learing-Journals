1. Creating Lists
- ==Lists can contain values of different types, can be changed after creation, and can contain duplicate elements.==
2. Accessing Elements by Index
- A list with n elements has non-negative indices from 0 to n - 1.
3. Slicing Lists
- ==Slicing syntax: a[start:stop:step]; the stop position is excluded.==
- ==Leaving all fields blank, as in a[::], returns a shallow copy containing all elements.==
- ==A negative step traverses the list from right to left.==
4. Changing List Elements
- Assign a new value through the element's index.
5. List Methods
+ ==append(): Add an element to the end of the list.==
+ ==extend(): Add multiple elements.==
+ ==insert(index, value): Insert an element at a position.==
+ ==remove(value): Remove the first element with the given value.==
+ ==pop(index): Remove and return the element at the given index.==
- If the index is omitted, pop() removes and returns the last element.
+ ==clear(): Remove all elements.==
+ ==index(value): Find the position of a value.==
+ ==count(value): Count how many times a value occurs.==
+ ==sort(): Sort the list in place in ascending order.==
- ==a.sort()== sorts in place and returns None; use 'a.sort(reverse=True)' for descending order or 'a.sort(key=len)' to sort by length.
+ ==reverse(): Reverse the list in place.==
+ ==copy(): Create a shallow copy of the list.==
6. ==Deleting Elements with del==
7. List Operators
+ ==Use + to concatenate two lists.==
+ ==Use * to repeat a list.==
+ ==Use in or not in to check for an element.==
+ ==Lists can be compared with comparison operators.==
8. Common Functions for Lists
+ ==len(): Return the number of elements.==
+ ==sum(): Return the sum of numeric elements.==
+ ==min() and max(): Find the minimum and maximum values.==
+ ==sorted(): Return a new list containing the elements in ascending order.==
- ==reversed(a) returns a reverse iterator; use list(reversed(a)) to create a new list.==
+ ==any(): Return True if at least one element is truthy.==
+ ==all(): Return True if every element is truthy.==
9. Iterating over a List
+ ==Direct iteration: for item in a==
+ ==Iterate by index: for index in range(len(a))==
+ ==Iterate with enumerate: for index, value in enumerate(a)==
- Pass start=n to enumerate() to begin the indices at n.
- To iterate with while, initialize an index and update it on each iteration.
Example:
    a = [10, 20, 30]
    index = 0
    while index < len(a):
        print(a[index])
        index += 1
10. List Comprehensions
- List comprehensions provide a concise way to create lists.
+ ==[expression for variable in range()]==
+ ==[expression for variable in iterable if condition]==
+ ==[value_if_true if condition else value_if_false for item in iterable]==
11. map() and filter()
+ ==map(): Transform each element.==
Example: list(map(lambda item: expression, a))
+ ==filter(): Keep elements that satisfy a condition.==
Example: list(filter(lambda item: condition, a))
12. Iterating over Multiple Lists with zip()
+ ==for item1, item2 in zip(a, b)==
- ==zip(a, b) returns an iterator; list(zip(a, b)) creates a list of tuples.==
13. Removing Duplicate Elements
- ==list(set(a)) removes duplicates but does not guarantee the original order; elements must be hashable.==
+ ==list(dict.fromkeys(a)) removes duplicates while preserving insertion order; elements must be hashable.==
14. Reading a List from User Input
+ Create an empty list and decide how many elements to read.
+ Loop with for i in range(count).
+ Read a value during each iteration.
+ Append each value to the list.
15. Converting Lists to Other Data Types
- =="".join(a) joins string elements. Convert numeric elements to strings first: "".join(map(str, a)).==
+ ==Use split() to convert a string into a list of substrings.==
16. Assigning Multiple Variables with Unpacking
Example: numbers = [1, 2, 3]; a, b, c = numbers  # a=1, b=2, c=3
    numbers = [1, 2, 3, 4, 5]
    first, *middle, last = numbers  # first=1, middle=[2, 3, 4], last=5
17. Searching a List
+ Check whether a value exists.
+ Find the index of a value.
+ Find all indices containing a value.
18. Two-Dimensional Lists (Matrices)
+ Use two indices to access an element. Using one index returns a row.
+ Use nested for loops to traverse a matrix.
+ Create a matrix using nested lists.
19. List References and Copying
+ Direct assignment does not create a copy; both variables refer to the same list.
Example:
    a = [1, 2, 3]
    b = a
    b.append(4)
    print(a)  # [1, 2, 3, 4]
+ Create a shallow copy:
Example:
    b = ==a.copy()==
    b = list(a)
    b = a[:]
+ A shallow copy of a nested list still shares its inner lists.
Example:
    a = [[1, 2], [3, 4]]
    b = a.copy()
    b[0][0] = 99
    print(a)  # [[99, 2], [3, 4]]
- Use copy.deepcopy() to recursively copy nested objects.
Example:
    import copy
    b = copy.deepcopy(a)
20. Advanced Sorting
+ To sort tuples by an item, provide a key such as key=lambda item: item[index].
21. Using a List as a Stack
+ ==Use append() to push an item and pop() to remove the last item.==
22. Using a List as a Queue
+ ==For a small queue, append() and pop(0) can be used; pop(0) shifts the remaining elements.==
+ ==For a larger queue, use collections.deque and popleft().==
23. Basic Time Complexities
+ Index access: O(1)
+ Append at the end: O(1) amortized
+ pop() from the end: O(1)
+ Insert at the beginning: O(n)
- Removing the first item with pop(0) takes O(n), where n is the list length, because the remaining items must shift.
+ Membership test with in: O(n)
+ index(): O(n)
+ remove(): O(n)
+ sort(): O(n log n)

24. Arrays as a Data Structure
- An array is an indexed sequence of elements. Traditional arrays usually store elements of the same data type in contiguous memory.
- The index identifies an element's position. In a zero-based array, the first element is at index 0.
- If elements occupy a fixed number of bytes, a program can calculate an element's address from the base address, index, and element size. This is why accessing an element by index is O(1).
- Arrays are useful when a program needs to store related values and access them by position.

25. Static and Dynamic Arrays
- ==A **static array** has a fixed capacity decided when it is created. Its capacity cannot normally be changed in place.==
- ==A **dynamic array** can grow when more elements are added. When its current storage is full, an implementation may allocate a larger block and copy the elements into it.==
- Resizing can take O(n), but dynamic arrays typically reserve extra capacity so repeated appends take O(1) amortized time.
- Python's built-in `list` behaves as a dynamic array, but it is not the same as a low-level typed array: a Python list can contain values of different types, and CPython lists store references to Python objects.
- Other languages and libraries may provide typed arrays with different memory and resizing behavior.

26. Array Operations and Time Complexity
+ Access an element by index: O(1).
+ Search for a value without a known index: O(n) in the general case, because elements may need to be checked one by one.
+ Traverse all elements: O(n).
+ Insert or delete at the beginning or middle: O(n), because later elements may need to shift.
+ Append to a dynamic array: O(1) amortized; an individual append that triggers resizing can take O(n).
- Big O describes how an operation's time or space requirements grow as the input size grows; it does not specify an exact runtime in seconds.

27. Source
- codebasics: Arrays - Data Structures & Algorithms Tutorials in Python #3 https://www.youtube.com/watch?v=gDqQf4Ekr2A
