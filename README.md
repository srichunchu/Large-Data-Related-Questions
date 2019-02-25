# Big Data Related Questions/Details

**Given a text file of size say 100GB? Task is to find first non repeating word in this file?
constraints: You can traverse the file only once.**

**Approach - 1:**

1. Read the file in chunks (either by number of rows OR bytes)

2. Maintain 2 data structures - a Hashmap and a Doubly LinkedList

3. If a word is not present in the hashmap:
3.1 add a node at the tail of the doubly linked list
3.2 insert into hashmap key = word, value = pointer(reference) to the node created in step 3.1

4. If the word is present in the hashmap(it's a duplicate):
4.1 Remove the node from doubly linked list(BUT NOT FROM HASHMAP)
4.2 Set the value of the key for this word in the hashmap to be null

once done reading the entire file, return head from doubly linkedlist.

Time complexity:
Adding/Deleting/Searching in Hashmap - Expected O(1)
Adding/Deleting a node from Doubly linked list - O(1) because a link to the node is stored in the hashmap so no need to search the DLL for deleting that node O(w) where w is the total number of words in the file

**Paxos Algorithm**

1. http://www.beyondthelines.net/algorithm/basic-paxos/#more-351
2. http://www.beyondthelines.net/algorithm/multi-paxos/#more-374

**Bloom Filter Use cases and References**
1. Sign Up -> Checking whether Username already exists or not
2. One Hit wonders -> Akamai & Facebook uses bloom filters to avoid caching the items that are very rarely searched or searched only once
3. https://medium.com/datadriveninvestor/bloom-filter-a-simple-but-interesting-data-structure-37fd53b11606
4. http://softwareas.com/bloom-filters-and-recommendation-engines/
5. https://www.quora.com/What-are-the-best-applications-of-Bloom-filters
6. https://cs.unc.edu/~fabian/courses/CS600.624/slides/bloomslides.pdf
