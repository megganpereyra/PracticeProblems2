# Practice this probles for this module


## Problem 1: ArrayList


In this practice, you will build a class to implement a special array list that stores its values in increasing order. First, you will do this using the Java ArrayList class. Then you will do this using a class that implements an array list directly using an array. Remember to work with your group member(s).
Clone the GitHub link.
https://github.com/itamames/Lecture5


This project contains a CalendarDate class that models a calendar date with a month, day and year (e.g. 7/4/1776).
A CalendarDate implements the Comparable interface which requires it to have a compareTo method.


```text
Using the compareTo method: If we have two objects a and b that are Comparable, then the method call a.compareTo(b) returns a positive integer if a is "greater" than b, a negative integer if a is "less" than b, or 0 if they are the same. For dates, the comparison is based on chronological order.


Example: If a is the date 12/4/1967 and b is the date 6/29/1951, the expression a.compareTo(b) returns a positive integer since a comes after b chronologically. (That is, a is "greater" than b in time.)
```


1) Read through the compareTo method in the CalendarDate class and explain how it works to your lab partner(s).


2) Examine the Problem1Tester class. This class contains a main method that creates an ArrayList of CalendarDate objects. The goal is to add the dates so that the list is always sorted in chronological order after each insert. Complete the insert method to satisfy this goal.


* HINT: Since the list should be sorted as you insert the next date, search for the correct insert point and then add the date there using the add method of the ArrayList class.


3) The OrderedArrayList class models an array list that always keeps its elements in sorted order without duplicates. The ordered array list is implemented using an array such that the entries in the list are stored in the array in increasing order in positions 0 to numData-1.
* Note that the class is defined such that the entries in the ordered array list must implement the Comparable interface so we can compare them using the compareTo method.


Complete the add method that inserts the new entry into the correct place in the array so that the entries in the array are stored in increasing order. If the new entry is inserted into the array, return true. If the new entry is already in the array, do not change the array and return false. The user of this list doesn't have to search for the correct insert point to add the entry; this method will do the work.


4) Test your code with the supplied testers (CalendarDateTester and StringTester). Your method should work for calendar dates and strings and for any other Comparable objects. (Why? Look at the OrderedArrayList class and see how its generic type is defined.)

Problem 2: ArrayList
