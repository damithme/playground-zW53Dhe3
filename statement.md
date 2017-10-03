## Overview
We discussed how to implement the Linked List in [here](https://tech.io/playgrounds/d4e9203aa1493fb4785624abeb8c56eb7896/linked-list-data-structure). In this tutorial, we’re going to implement insertion a Node at given position.

## Insert a Node at Nth Position

***Steps***
1. If Head is null and position is not 0. Then exit it.
2. If Head is null and position is 0. Then insert new Node to the Head and exit it.
3. If Head is not null and position is 0. Then the Head reference set to the new Node. Finally, new Node set to the Head and exit it.
4. If not, iterate until finding the Nth position or end.

```java
public void insertNth(int data, int position) {
    //create new node.
    Node node = new Node();
    node.data = data;
    node.nextNode = null;

    if (this.head == null) {
      //if head is null and position is zero then exit.
      if (position != 0) {
       return;
      } else { //node set to the head.
       this.head = node;
      }
    }

    if (head != null && position == 0) {
      node.nextNode = this.head;
      this.head = node;
      return;
    }

    Node current = this.head;
    Node previous = null;

    int i = 0;

    while (i < position) {
      previous = current;
      current = current.nextNode;

      if (current == null) {
        break;
      }

       i++;
      }

      node.nextNode = current;
      previous.nextNode = node;
}
```

## Complete Example
```java runnable
class Node {
    int data;
    Node nextNode;
}
public class LinkedList {

    private Node head;

    // { autofold
    public void insert(int data) {
        //create a new Node and store a data.
        Node node = new Node();
        node.data = data;
        node.nextNode = null;

        //check the head is null or not.
        //if head is null, assign the Node and exit.
        if (this.head == null) {
            head = node;
            return;
        }

        //assign a head into the temp Node and loop it until find the null reference.
        Node tempNode = this.head;
        while (tempNode.nextNode != null) {
            tempNode = tempNode.nextNode;
        }

        //assign new node.
        tempNode.nextNode = node;
    }
    // }

    public void insertNth(int data, int position) {
        //create new node.
        Node node = new Node();
        node.data = data;
        node.nextNode = null;


        if (this.head == null) {
            //if head is null and position is zero then exit.
            if (position != 0) {
                return;
            } else { //node set to the head.
                this.head = node;
            }
        }

        if (head != null && position == 0) {
            node.nextNode = this.head;
            this.head = node;
            return;
        }

        Node current = this.head;
        Node previous = null;

        int i = 0;

        while (i < position) {
            previous = current;
            current = current.nextNode;

            if (current == null) {
                break;
            }

            i++;
        }

        node.nextNode = current;
        previous.nextNode = node;
    }

    // { autofold
    public void print() {
        if (this.head == null) {
            return;
        }
        //print all nodes
        Node tempNode = this.head;
        while (tempNode != null) {
            System.out.print(tempNode.data + "->");
            tempNode = tempNode.nextNode;
        }
        System.out.println("NULL");
    }
    // }

}
public class Main {

  public static void main(String[] args) {
      LinkedList ls = new LinkedList();
      ls.insert(10);
      ls.insert(20);
      ls.insert(30);
      ls.print();
      ls.insertNth(25, 2);
      ls.print();
      ls.deleteNth(3);
      ls.print();
  }
}
```
```java runnable
// { autofold
public class Main {

public static void main(String[] args) {
// }

String message = "Hello World!";
System.out.println(message);

//{ autofold
}

}
//}
```

Original post can find it [here](http://mydevgeek.com/linked-list-insertion-deletion-nth-position/)
