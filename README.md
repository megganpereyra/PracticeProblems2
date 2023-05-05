# Practice this problems for this module


## Problem 1: ArrayList


In this practice, you will build a class to implement a special array list that stores its values in increasing order. First, you will do this using the Java ArrayList class. Then you will do this using a class that implements an array list directly using an array. Remember to work with your group member(s).


This project contains a CalendarDate class that models a calendar date with a month, day and year (e.g. 7//4//1776).
A CalendarDate implements the Comparable interface which requires it to have a compareTo method.

Using the compareTo method: 
* If we have two objects a and b that are Comparable, then the method call a.compareTo(b) returns a positive integer 
* if a is "greater" than b, a negative integer if a is "less" than b, or 0 if they are the same. 
* For dates, the comparison is based on chronological order.


Example: 

If a is the date 12/4/1967 and b is the date 6/29/1951, the expression a.compareTo(b) returns a positive integer since a comes after b chronologically. (That is, a is "greater" than b in time.)



1) Read through the compareTo method in the CalendarDate class and explain how it works to your lab partner(s).


2) Examine the Problem1Tester class. This class contains a main method that creates an ArrayList of CalendarDate objects. The goal is to add the dates so that the list is always sorted in chronological order after each insert. Complete the insert method to satisfy this goal.


* HINT: Since the list should be sorted as you insert the next date, search for the correct insert point and then add the date there using the add method of the ArrayList class.


3) The OrderedArrayList class models an array list that always keeps its elements in sorted order without duplicates. The ordered array list is implemented using an array such that the entries in the list are stored in the array in increasing order in positions 0 to numData-1.
* Note that the class is defined such that the entries in the ordered array list must implement the Comparable interface so we can compare them using the compareTo method.


Complete the add method that inserts the new entry into the correct place in the array so that the entries in the array are stored in increasing order. If the new entry is inserted into the array, return true. If the new entry is already in the array, do not change the array and return false. The user of this list doesn't have to search for the correct insert point to add the entry; this method will do the work.


4) Test your code with the supplied testers (CalendarDateTester and StringTester). Your method should work for calendar dates and strings and for any other Comparable objects. (Why? Look at the OrderedArrayList class and see how its generic type is defined.)

## Problem 2: Stack


1) Create a new class named ArrayStack2 that implements a stack where the top of the stack is always stored in position 0 of the array. 
* When an element is pushed on this stack, the elements on the stack must be shifted to make room for the new element. 
* Likewise, when an element is popped from this stack, the elements on the stack must be shifted the opposite direction to fill in the gap left by the removed element. 
* Your class should implement the LIFOStack interface so it must include all of the required methods specified by that interface in the project.

2) Test your ArrayStack2 class by changing the PostfixEvaluator class so that it uses a stack of type ArrayStack2 instead of ListStack.

3) Create a new class Calculator that contains a main method that asks the user for an expression in infix notation and computes its value by first converting it to postfix and then evaluating its value. 
* The infix expression must be input with spaces between each token. (This should not require a lot of code... THINK.)

4) The postfix evaluator and infix-to-postfix generators can handle input of multiple digit positive integers as operands. 
* How does it know if a token is an integer? 
* What happens if someone enters a token like 7UP that looks like an integer initially but really isn't? 
* Modify the infix-to-postfix converter to deal with this case by throwing a syntax error exception. 
* Catch this in your calculator and ask the user to input a valid infix expression until the user finally does.

## Problem 3 Queue

In this problem, you will work on a simulation that uses queues to analyze a problem for a supermarket. The manager of the supermarket wants to analyze whether there should be a separate line (queue) of customers for each cash register or a single line that serves all cash registers so that once a cash register is available, the next person on line goes directly to that cash register to check out.

## EXERCISES

This practice contains a Customer class that models a customer in the supermarket. Each customer keeps track of the time when the customer enters the queue and how long it will take for the customer to check out once the customer arrives at the cash register.

There are also two simulator classes, Simulation1 and Simulation2. Each simulation has three parameters, the probability that a customer arrives each minute, the number of registers in the market, and the total number of simulated minutes. The simulation then has a loop that simulates one minute of time in the market.

1) Read the comments in each Simulation class and complete the required code.

2) Run each simulator with the given parameters and see what the average waiting time is for a customer. Then increase the arrival probability by 0.1 at a time and look at the average waiting time. (The probability should not exceed 1.0 total.) 

3) Try to decide which queue policy is better for the customers.
