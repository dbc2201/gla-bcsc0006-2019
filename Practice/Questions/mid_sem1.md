## Data Structures & Algorithms using Java

### Practice Questions



1. Describe three uses of the list structure as a way of organising information that you are familiar with.

2. Describe the order of magnitude of each of the following functions using Big-O notation:

   1. N<sup>2</sup>+ 3N
   2. 3N<sup>2</sup> + N
   3. N<sup>5</sup>< + 100N<sup>3</sup> + 245
   4. 3Nlog<sub>2</sub> N + N<sup>2</sup>
   5. 1 + N + N<sup>2</sup> + N<sup>3</sup> + N<sup>4</sup>

3. Describe the order of magnitude of each of the following code sections, using
   Big-O notation:

   1. ```java
      count = 0;
      for (i = 1; i <= N; i++)
          count++;
      ```

   2. ```java
      count = 0;
      for (i = 1; i <= N; i++)
          for (j = 1; j <= N; j++)
              count++;
      ```

   3. ```java
      value = N;
      count = 0;
      while (value > 1)
      {
          value = value / 2;
          count++;
      }
      ```

   4. ```java
      count = 0;
      value = N;
      value = N * (N - 1);
      count = count + value;
      ```

   5. ```java
      count = 0;
      for (i = 1; i <= N; i++)
          count++;
      for (i = N; i >= 0; i--)
          count++;
      ```

4. Consider the following two algorithms that initialize every element in an N-
   element array to zero.

   ```
   Algorithm Init1 
   elements[0] = 0;
   elements[1] = 0;
   elements[2] = 0;
   elements[3] = 0;
   .
   .
   .
   elements[N–1] = 0;
   
   Algorithm Init2
   for (index = 0; index < N; index++)
   	elements[index] = 0;
   ```

   What is the Big-O efficiency of the first algorithm? Of the second algorithm? Explain.

5. Algorithm 1 does a particular task in a “time” of N 3 , where N is the number of elements processed. Algorithm 2 does the same task in a “time” of 3N + 1000.

   1. What is the Big-O efficiency of each algorithm?
   2. Which algorithm is more efficient by Big-O standards?
   3. Under what conditions, if any, would the “less efficient” algorithm execute more quickly than the “more efficient” algorithm?

6. Consider an ADT called `SquareMatrix` . (The matrix can be represented by a two-dimensional array of integers with `m` rows and `n` columns.)

   1. Write the specification for the ADT in Java. Include the following operations (parameters are already listed for the first two operations; for the remaining operations you must determine which parameters to use yourself, as part of the exercise):
      `makeEmpty(n)`  : which sets the first `n` rows and columns to zero.  
      `storeValue(i, j, value)` , which stores `value` into the position at row `i` , column `j`.  
      `add()` , which adds two matrices together.  
      `subtract()` , which subtracts one matrix from another.  
      `copy()` , which copies one matrix into another.  
   2. Create a Java class that implements the ADT. Assume a maximum size of 50 rows and columns.

7. True or False?

   1. A stack is a first in, first out structure.
   2. The item that has been in a stack the longest is at the “bottom” of the stack.
   3. f you `push` five items onto an empty stack and then `pop` the stack five times, the stack will be empty again.

8. Based on our Stack ADT specification, an application programmer has two ways to check for an empty stack. Describe them and discuss when one approach might be preferable to the other approach.

9. Your friend Bill says, “The `push` and `pop` stack operations are inverses of each other. Therefore performing a `push` followed by a `pop` is always equivalent to performing a `pop` followed by a `push` .  You get the same result!” How would you respond to that? Do you agree?

10. Two stacks of positive integers are needed, both containing integers with values less than or equal to 1000. One stack contains even integers; the other contains odd integers. The total number of elements in the combined stacks is never more than 200 at any time, but we cannot predict how many are in each stack. (All of the elements could be in one stack, they could be evenly divided, both stacks could be empty, and so on.) Can you think of a way to implement both stacks in one array?

    1. Draw a diagram of how the stacks might look.
    2. Write the definitions for such a double-stack structure.
    3. Implement the `push` operation; it should store the new item into the correct
       stack according to its value (even or odd).

11. True or False?

    1. A queue is a “first in, first out” structure.
    2. The element that has been in a queue the longest is at the “rear” of the queue.
    3. If you `enqueue` five elements into an empty queue and then `dequeue` five elements, the queue will be empty again.
    4. If you `enqueue` five elements into an empty queue and then perform the `isEmpty` operation five times, the queue will be empty again.

12. Indicate which would be a suitable data structure to use in each of the following applications from list, stack or queue.

    1. An ailing company wants to evaluate employee records so that it can lay off some workers on the basis of service time (the most recently hired employees are laid off first).
    2. A program is to keep track of patients as they check into a clinic, assigning them to doctors on a “first come, first served” basis.
    3. A program to solve a maze is to backtrack to an earlier position (the last place where a choice was made) when a dead-end position is reached.
    4. An inventory of parts is to be processed by part number.
    5. An operating system is to process requests for computer resources by allocating the resources in the order in which they are requested.
    6. A grocery chain wants to run a simulation to see how average customer wait time would be affected by changing the number of checkout lines in its stores.
    7. A dictionary of words used by a spelling checker is to be initialized.
    8. Customers are to take numbers at a bakery and be served in order when their number comes up.
    9. Gamblers take numbers in the lottery and win if their numbers are picked.

13. Based on our Queue ADT specification, an application programmer has two ways to check for an empty queue. Describe them and discuss when one approach might be preferable to the other approach.

14. Give examples from the “real world” of unsorted lists, sorted lists, indexed lists, lists that permit duplicate elements, and lists that do not permit duplicate elements.

15. Besides unsorted lists, sorted lists, and indexed lists, are there other potential varieties of lists? Describe a few of them informally.

16. We do not allow `null` elements on our lists. Why not? Describe some of the ramifications of removing this restriction, that is, of allowing `null` elements. You should include the potential effects on implementation details.

17. The specifications for our List ADT allow lists to contain duplicate elements. Describe how you would change the specifications if duplicate elements were not permitted.

18. Someone suggests that, instead of shifting list elements to the left when an object is removed, the array location holding that object should just be set to `null` . Discuss the ramifications of such an approach for each of our list type.

19. Consider the operation: `removeAll()`—removes all elements from the list that are equal to the argument element and returns an `int` indicating how many elements were removed. Design a method to be added to the `ListADT` class that implements the operation. Code and test your method.

20. Suppose we have a class called `Car` that models cars. This class has instance variables `year, make, model & price`. It also provides appropriate getter methods, including one called `getPrice()` that returns a value of type `int` indicating the price of “this” car. Implement a client method `totalPrice()`, which accepts a list of cars and returns an integer equal to the total cost of the cars on the list.