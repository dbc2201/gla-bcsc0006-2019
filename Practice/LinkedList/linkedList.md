# Linked Lists

- A linked list is a data structure that provides us with the ability to add or remove items anywhere 
in the list in constant `O(1)` time.
- A linked list is useful when we need to insert or remove elements at random locations.
- A linked is also useful when we need to do insertion and deletion frequently.
- We do not keep track of indices inside a linked list, hence we cannot tell the order of a node just by looking at it.

___

## Terminologies

- Head : The first node of a linked list.
- Tail : The last node of a linked list.
- Link Hopping/Node Hopping/Pointer Hopping: Moving from one node to another by following a next reference.

___

## Types of Linked Lists

1. Singly Linked List

    - The tail of a singly linked list will contain `null`.
    
2.     
    
___

## A Node 

![](./../../Images/node.png)

- A `Node` is a data structure that contains a data item and one or more links.
- A `linl` is a reference to a `node`.

Sample code for implementing a `node` in Java

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