# LRU-using-c
Here, I've created an LRU cache policy utilising the C programming language and data structure ideas. I created this using a binary search tree and a doubly linked list.
LRU cache policy:
LRU (Least Recently Used) cache policy is a popular caching strategy used in computer systems to manage the contents of a cache. The basic idea behind LRU is to keep track of the order in which items are accessed in the cache and evict the least recently used item when the cache reaches its maximum capacity.

Here's how LRU cache policy typically works:

    Tracking Access:
        When an item is accessed (read or written) in the cache, it is considered the most recently used item.
        The LRU policy maintains a record of the access order of items.

    Cache Maintenance:
        As the cache becomes full and a new item needs to be added, the LRU policy identifies and removes the least recently used item.
        This eviction ensures that the cache remains within its capacity limit.

    Updating Access Order:
        When an item already present in the cache is accessed again, it becomes the most recently used item.
        The LRU policy updates the access order, pushing the recently accessed item to the front of the order.

    Data Structures:
        Implementing LRU often involves the use of data structures such as a doubly linked list and a hash map.
        The linked list keeps track of the order of items, with the most recently used item at the front and the least recently used item at the end.
        The hash map allows quick lookup to determine whether an item is present in the cache and, if so, its corresponding node in the linked list.

    Complexity:
        While LRU is effective in preventing the cache from becoming stale with outdated or less frequently used data, implementing it efficiently may involve more complex data structures and operations.

LRU caching is commonly used in various applications, including databases, web servers, and file systems, where it helps improve performance by keeping frequently accessed data readily available in a limited-size cache.

The given code implements a simple Least Recently Used (LRU) cache policy using a combination of a Doubly Linked List, Binary Search Tree (BST), and a Binary Search Tree for Recording Application Usage.

Data Structures Used:

    Doubly Linked List:
        Purpose: Used for implementing the cache, with the most recently accessed element at the head and the least recently accessed at the tail.
        Operations:
            insertList: Inserts a new element at the head of the linked list.
            deleteLastList: Deletes the last (least recently used) element from the linked list.
            print: Prints the elements of the linked list.

    Binary Search Tree (BST):
        Purpose: Used for maintaining the cache with a specific application name and its corresponding address in the linked list.
        Operations:
            insertBST: Inserts a new node in the BST with the application name and its address in the linked list.
            deleteBST: Deletes a node from the BST based on the application name.
            searchBST: Searches for a node in the BST based on the application name.
            heightBST: Calculates the height of the BST.
            pred: Finds the predecessor node in the BST.
            succ: Finds the successor node in the BST.

    Binary Search Tree for Recording Application Usage:
        Purpose: Used for recording the usage statistics of each application, including hits and misses.
        Operations:
            insertRecord: Inserts a new node with application name and initializes hits and misses.
            searchRecord: Searches for a node in the recording BST based on the application name.
            Record_print: Prints the summary of application usage, including cache hits and misses.

Main Function:

    The main function simulates the LRU cache policy by taking user input and performing cache operations accordingly.
    Users can:
        Access an application (simulating a cache request).
        Display the current cache blocks.
        View the summary of application usage (hits and misses).
        Exit the program.

LRU Cache Policy Implementation Logic:

    Whenever a new application is accessed, the code checks if it is already in the cache using the BST.
    If the application is not in the cache, it is added to both the linked list and the BST, simulating a cache miss.
    If the application is already in the cache, it is moved to the head of the linked list, simulating a cache hit.
    The cache has a maximum size (cacheSize), and if it exceeds this size, the least recently used block is removed from both the linked list and the BST.

This code efficiently manages the cache using the LRU policy, maintaining a balance between cache size, application access, and recording usage statistics.
