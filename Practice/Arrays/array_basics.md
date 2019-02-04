# Basic Programs for Arrays in Java

1. Write a program that declares a 10-element array of `int` , uses a loop to initialize each element to the value of its index squared, and then uses another loop to print the contents of the array, one integer per line.

2. Write a program that declares a 10-element array of `Date` , uses a loop to initialize the elements to December 1 through 10 of 2005, and then uses another loop to print the contents of the array, one date per line.

3. Create an application that instantiates a `20 x 20` two-dimensional array of integers, populates it with random integers drawn from the range 1 to 100, and then outputs the index of the row with the highest  sum among all the rows and the index of the column with the highest sum among all the columns.

4. Assume that `numbers` is a large array of integers, currently holding `N` values in locations `0` through `N–1`.

   1. Insert the number `17` into location `N` of `numbers`.
   2. Shift all values in the `numbers` array to the “right” by one location to make room at location `0` for a new number without disrupting the order of the current values; insert the number `17` into location `0`.
   3. Randomly choose a location `L` from `0` to `N–1`; shift all the values in the `numbers` array, from location `L` to location `N–1`, to the right one location to make room at location `L` for a new number; insert the number `17` into location `L`.

5. Rainfall Class
   Write a `RainFall` class that stores the total rainfall for each of 12 months into an array of `doubles`. The program should have methods that return the following:  

   - the total rainfall for the year
   - the average monthly rainfall
   - the month with the most rain
   - the month with the least rain

   Demonstrate the class in a complete program.
   _Input Validation_: Do not accept negative numbers for monthly rainfall figures