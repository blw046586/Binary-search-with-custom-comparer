# Binary-search-with-custom-comparer
Binary search with non-integer lists
This book provides an implementation of binary search that operates on an integer list. But an implementation that can operate on lists of any type has more practical value. This lab focuses on a binary search implementation that uses a custom comparison method and so can search lists sorted based on different criteria.


Step 1: Inspect Comparer.py and DescendingComparer.py
File Comparer.py contains the Comparer class definition. Comparer has one method named compare(). compare() takes two arguments for two items to compare. compare(a, b) returns an integer:

greater than 0 if a > b,
less than 0 if a < b, or
equal to 0 if a == b.
File DescendingComparer.py contains the DescendingComparer class definition. DescendingComparer flips the greater and less than cases above and so can be used on lists sorted in descending order.


Step 2: Inspect Searcher.py
File Searcher.py contains the Searcher class definition. Searcher has one method named binary_search(). binary_search() has parameters for a sorted list to search, a key to search for, and a Comparer object. binary_search() must not use operators like < and > to compare list items. Instead, the comparer object's compare() method must be used.

Ex: Suppose binary_search() calls comparer.compare(sorted_list[mid], key) and 1 is returned. The 1 means that key, if present in the list, is in the low part of the list (at an index < mid). The list may be sorted ascending and comparer is a Comparer instance, or the list may be sorted descending and comparer is a DescendingComparer instance. But neither need be known to properly implement binary_search().

Step 3: Implement the Searcher class's binary_search() method
Implement the Searcher class's static binary_search() method in the Searcher.py file. The function should perform a binary search on the sorted list (first parameter) for the key (second parameter). binary_search() returns the key's index if found, -1 if not found. Compare a list element to the key using the compare() method of the comparer object passed as binary_search()'s last argument.

Some test cases exist in main.py to test binary_search() with both string searches and integer searches. Some lists are sorted in ascending order, others in descending order. The proper Comparer object is passed to each binary_search() call. Clicking the Run button will display test case results, each starting with "PASS" or "FAIL". Ensure that all tests are passing before submitting code.

Each test in main.py only checks that binary_search() returns the correct result, but does not check the number of comparisons performed. The unit tests that grade submitted code check both binary_search()'s return value and the number of comparisons performed. The last unit test also uses lists with element types other than integers and strings.
