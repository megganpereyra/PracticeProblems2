# Practice Problems 2

Q1) Suppose an ArrayList is implemented with an array, and the array doubles in size whenever the array fills up. Explain why adding an element to the end of the arraylist is considered a constant time operation in general.
```text
Todo
```

Q2) Suppose we have an ArrayList of N integer objects, sorted in increasing order. Consider the following algorithms for removing a particular Integer value from that ArrayList.
    * It is already known that this value is in the ArrayList.
    * Identify the best and worst case running times (using Big O) for each algorithm. Explain each of your answers.

a) Algorithm I: Perform a linear search to find the value, starting from the BEGINNING of the list. When the value is found, remove it by calling the ArrayList's remove(index) method.

```text
Todo
```

b) Algorithm II: Perform a linear search to find the value, starting from the END of the list. When the value is found, remove it by calling the ArrayList's remove(index) method.

```text
Todo
```
c) Algorithm III: Perform a binary search to find the value. When the value is found, remove it by calling the ArrayList's remove(index) method.

```text
Todo
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
Todo
```

b) What happens with this code if there are an even number of nodes? Explain with an example. Modify the method to deal with this situation in a reasonable manner.

```text
Todo
```

c) What is the runtime complexity of this method in big-O notation if the list has n elements?

```text
Todo
```

Q4) Consider a variant of the singly linked list that contains a "dummy node" at the beginning of the list with no data (i.e. the data field is always null). 

An empty list consists of a dummy node only. A list with n elements has n+1 nodes, the first node being the dummy node. The dummy node makes it easier to implement add and remove operations since the list can never be truly empty.

a) Rewrite the SinglyLinkedList constructor to create an "empty" list consisting of one dummy node.

```java
public SinglyLinkedList() { 
//todo
}
```
b) Rewrite the methods add and remove assuming the singly linked list always contains a dummy node.

```java
public void add(int index, E element) { 
//todo
} 
```

```java
public E remove(int index) { 
//todo
	return result; 
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
		//todo
	}
```
b) Complete the push method for the SmithersStack class and determine the worst-case runtime complexity of push assuming that the stack contains n elements.

```java
	public void push(E element) {
		//todo
	}
```


Q6) Write a program to sort a stack in ascending order. You should not make any assumptions about how the stack is implemented. The following are the only functions that should be used to write this program: push, pop, peek, and isEmpty.

peek - an operation that returns the value of the top element of the stack without removing it. 

Algorithm:
Sorting can be performed with one more stack.
Iterate until the original stack is empty and in each iteration, pop an element from the original stack, while the top element in the second stack is bigger than the removed element, pop the second stack and push it to the original stack. 

```java
public static Stack<Integer> sort(Stack<Integer> s)
{
     //todo
}
```
