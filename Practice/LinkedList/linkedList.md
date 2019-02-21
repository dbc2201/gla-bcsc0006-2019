# Linked Lists

## Disadvantages of using Arrays

1. In an unsorted array, searching is slow.
2. In a sorted array, inserting is slow.
3. Deletion is slow in both sorted and unsorted arrays.
4. The size of an array cannot be modified after it is created.

___

- A linked list is a data structure that provides us with the ability to add or remove items anywhere 
in the list in constant `O(1)` time.
- A linked list is useful when we need to insert or remove elements at random locations.
- A linked is also useful when we need to do insertion and deletion frequently.
- We do not keep track of indices inside a linked list, hence we cannot tell the order of a node just by looking at it.
- LinkedLists need not be stored consecutively in the memory.

___

## Terminologies

- Head : The first node of a linked list.
- Tail : The last node of a linked list.
- Link Hopping/Node Hopping/Pointer Hopping: The tail of a list can be found by traversing the
                                             linked list— starting at the head and moving from one node to another by following
                                             each node’s next reference. We can identify the tail as the node having null as its
                                             next reference.

___

## Types of Linked Lists

1. Singly Linked List

    - The tail of a `singly` linked list will contain `null`.  
    **LIMITATIONS**
    - Insertion at the front of the list is `O(1)`. Insertion at other positions is `O(n)`, where `n` is
the size of the list.
    - We can only insert/remove a node if we have the reference to its predecessor node.
    - We can move in only one direction, starting at the list's head.
    
2. Doubly Linked List

    - A `Doubly` linked list allows us to go in both direction, `forward` and `backward`.  
    - They allow a greater variety of `O(1)-time` update operations, including insertions and deletions at arbitrary
      positions within the list.
    - In order to avoid some special cases when operating near the boundaries of a doubly
      linked list, it helps to add special nodes at both ends of the list: a `header` node at the
      beginning of the list, and a `trailer` node at the end of the list. These “dummy” nodes
      are known as `sentinels (or guards)`, and they do not store elements of the primary
      sequence.
    
3. Circular Linked List

    - There is no `head` or `tail` in a `circular` linked list.
    - Instead of having the last node's next pointer be `null`, it points back to the first node.
    
___

## A Node 

![](./../../Images/node.png)

- A `Node` is a data structure that contains a data item and one or more links.
- A `linl` is a reference to a `node`.

Sample code for implementing a `node` in a Singly Linked List in Java

```java
public class Node {
    private int data;
    private Node next;
  
    public int getData() {
      return data;
    }
  
    public void setData(int data) {
      this.data = data;
    }
  
    public Node getNext() {
      return next;
    }
  
    public void setNext(Node next) {
      this.next = next;
    }
  
    public Node(int data, Node next) {
      this.data = data;
      this.next = next;
    }
} 
```

___

## The Linked List of Nodes

![](./../../Images/linkedList.png)
___

## Help Links

1. [Visualize Linked Lists](https://visualgo.net/en/list)
2. [Linked Lists by HackerRank](https://www.youtube.com/watch?v=njTh_OwMljA)
3. [Linked Lists on Wikipedia](https://en.wikipedia.org/wiki/Linked_list)

___

## EXTRA

```
FOR PYTHON PROGRAMMERS
The Python list class is similar to the Java ArrayList class. Both can store a collection of
objects and both automatically expand when extra space is needed. Both have methods
to add elements, insert elements, and get the list length. However, you cannot use array
index notation (e.g., scores[3] ) with an ArrayList but you can with a Python list .
```