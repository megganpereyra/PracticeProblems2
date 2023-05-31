# Practice Problems 2
## Meggan Pereyra


Q1) Suppose an ArrayList is implemented with an array, and the array doubles in size whenever the array fills up. Explain why adding an element to the end of the arraylist is considered a constant time operation in general.
```text
The resizing operation itself takes linear time, the frequency of resizing is reduced significantly due to the exponential growth of the array's capacity. This allows for a constant time(in other words 
o(n)) complexity on average when adding elements to the end of the ArrayList.
```

Q2) Suppose we have an ArrayList of N integer objects, sorted in increasing order. Consider the following algorithms for removing a particular Integer value from that ArrayList.
    * It is already known that this value is in the ArrayList.
    * Identify the best and worst case running times (using Big O) for each algorithm. Explain each of your answers.

a) Algorithm I: Perform a linear search to find the value, starting from the BEGINNING of the list. When the value is found, remove it by calling the ArrayList's remove(index) method.

```text
Best case O(1), worst case O(n) and heres why: If the value to be removed is the first element in the ArrayList, the linear search will find it immediately, and removing it by calling the ArrayList's remove(index) method will take constant time. If the value to be removed is at the end of the ArrayList or not present in the list, the linear search will have to iterate through all N elements to find it. Removing it by calling the ArrayList's remove(index) method will also take O(N) time since all elements after the index need to be shifted to fill the gap left by the removed element.

```

b) Algorithm II: Perform a linear search to find the value, starting from the END of the list. When the value is found, remove it by calling the ArrayList's remove(index) method.

```text
Best case O(1) and worst case O(n), heres why: If the value to be removed is the last element in the ArrayList, the linear search will find it immediately, and removing it by calling the ArrayList's remove(index) method will take constant time. If the value to be removed is at the beginning of the ArrayList or not present in the list, the linear search will have to iterate through all N elements to find it. Removing it by calling the ArrayList's remove(index) method will also take O(N) time since all elements after the index need to be shifted to fill the gap left by the removed element. 
```
c) Algorithm III: Perform a binary search to find the value. When the value is found, remove it by calling the ArrayList's remove(index) method.

```text
Best case O(log n) and worst case O(n), heres why: If the value to be removed is found at the middle element during the binary search, it will take O(log N) time to find the value. After finding the value, removing it by calling the ArrayList's remove(index) method will take O(N) time since all elements after the index need to be shifted to fill the gap left by the removed element. If the value to be removed is at either end of the ArrayList or not present in the list, the binary search will still take O(log N) time to determine the value is not present. After that, removing the element by calling the ArrayList's remove(index) method will take O(N) time since all elements after the index need to be shifted to fill the gap left by the removed element.
```

Q3) Consider the following method for the SinglyLinkedList class that works on a linked list.
```java
public E mystery() {
	Node<E> p = head;
	Node<E> q = head.next;
	while (q != null) {
		p = p.next;
		q = q.next.next;
	}
	return p.data;
}
```

a) What does this method do if there are an odd number of nodes? Explain by tracing this code with a list with 9 nodes.

```text
 the method mystery() will find and return the data of the middle node in the linked list. To break it down:
 1. Initialize two pointers, p and q, to the head node of the linked list.
2. In the first iteration of the while loop, p moves one step forward (p = p.next) and q moves two steps forward (q = q.next.next).
p -> node1
q -> node3
3. In the second iteration, p moves one step forward again (p = p.next) and q moves two steps forward.
p -> node2
q -> node5
4.In the third iteration, p moves one step forward, and q moves two steps forward.
p -> node3
q -> node7
5. In the fourth iteration, p moves one step forward, and q moves two steps forward.
p -> node4
q -> null (reached the end of the list)
6. The while loop terminates since q is null.
7. The method returns the data (p.data) of the middle node, which is node4.
```

b) What happens with this code if there are an even number of nodes? Explain with an example. Modify the method to deal with this situation in a reasonable manner.

```text
If there are an even number of nodes, the code will encounter a problem. Let's say we have a linked list with 8 nodes, When p reaches node4, q will be pointing to node8. In the next iteration, p will move one step forward (p = p.next) and become node5. However, q will try to move two steps forward (q = q.next.next) but will encounter a NullPointerException since q.next is null.
```

```java
public E mystery() {
	Node<E> p = head;
	Node<E> q = head.next;
	while (q != null && q.next != null) {
		p = p.next;
		q = q.next.next;
	}
	return p.data;
}

```

c) What is the runtime complexity of this method in big-O notation if the list has n elements?

```text
The runtime complexity of this method is O(n/2), which simplifies to O(n), where n is the number of elements in the linked list. This is because the while loop traverses the linked list, incrementing p by one and q by two, until q reaches the end of the list. Since q moves twice as fast as p, the loop will execute approximately n/2 times. Therefore, the runtime complexity is linear, or O(n), in big-O notation.
```

Q4) Consider a variant of the singly linked list that contains a "dummy node" at the beginning of the list with no data (i.e. the data field is always null). 

An empty list consists of a dummy node only. A list with n elements has n+1 nodes, the first node being the dummy node. The dummy node makes it easier to implement add and remove operations since the list can never be truly empty.

a) Rewrite the SinglyLinkedList constructor to create an "empty" list consisting of one dummy node.

```java
public SinglyLinkedList() {
    head = new Node<>(null); // Create a dummy node with null data
    size = 0; // Set the size of the list to 0 since there are no actual elements yet
}

```
b) Rewrite the methods add and remove assuming the singly linked list always contains a dummy node.

```java
public void add(int index, E element) {
    if (index < 0 || index > size) {
        throw new IndexOutOfBoundsException("Invalid index: " + index);
    }

    Node<E> newNode = new Node<>(element);
    Node<E> current = head;
    for (int i = 0; i < index; i++) {
        current = current.next;
    }

    newNode.next = current.next;
    current.next = newNode;
    size++;
}

public E remove(int index) {
    if (index < 0 || index >= size) {
        throw new IndexOutOfBoundsException("Invalid index: " + index);
    }

    Node<E> current = head;
    for (int i = 0; i < index; i++) {
        current = current.next;
    }

    Node<E> removedNode = current.next;
    current.next = removedNode.next;
    removedNode.next = null;
    size--;

    return removedNode.data;
}

```

Q5)  Smithers decides to implement his stack, called SmithersStack< E >. The contents of the stack are stored in a field called data of type ArrayList< E>, where INDEX 0 represents the TOP of the stack. 

```java
public class SmithersStack<E>
{
        private ArrayList<E> data;  //top element at index 0

        //constructors and other methods not shown
}
```


a) Complete the pop method for the SmithersStack class and determine the worst-case runtime complexity of pop assuming that the stack contains n elements. If the stack is empty, return null in this case.

```java
public E pop() {
    if (data.isEmpty()) {
        return null; // Stack is empty, return null
    }
    return data.remove(0); // Remove and return the element at index 0 (top of the stack)
}

```
b) Complete the push method for the SmithersStack class and determine the worst-case runtime complexity of push assuming that the stack contains n elements.

```java
public void push(E element) {
    data.add(0, element); // Add the element at index 0 (top of the stack)
}

```


Q6) Write a program to sort a stack in ascending order. You should not make any assumptions about how the stack is implemented. The following are the only functions that should be used to write this program: push, pop, peek, and isEmpty.

peek - an operation that returns the value of the top element of the stack without removing it. 

Algorithm:
Sorting can be performed with one more stack.
Iterate until the original stack is empty and in each iteration, pop an element from the original stack, while the top element in the second stack is bigger than the removed element, pop the second stack and push it to the original stack. 

```java
import java.util.Stack;

public static Stack<Integer> sort(Stack<Integer> s) {
    Stack<Integer> sortedStack = new Stack<>();

    while (!s.isEmpty()) {
        int temp = s.pop();

        while (!sortedStack.isEmpty() && sortedStack.peek() > temp) {
            s.push(sortedStack.pop());
        }

        sortedStack.push(temp);
    }

    return sortedStack;
}
ff
```
