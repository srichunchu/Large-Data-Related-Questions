# Large-Data-Related-Questions

Given a text file of size say 100GB? Task is to find first non repeating word in this file?
constraints: You can traverse the file only once.

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
