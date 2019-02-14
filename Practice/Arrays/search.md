# Searching in Arrays using Java

___  

## Types of search  
### Linear Search  
### Binary Search  

___

## Linear Search

- Linear search is also known as `sequential search`.
- It is a simple method to search an array for a particular value.
- It compares every element of the array one by one with the value to search until 
a match is found.
- It is most commonly used when the array is unsorted.

### Algorithm for Linear Search

```
1. Initialize a variable 'position' to -1
2. Initialize a variable 'i' to 0
    [Loop starts]
3. Repeat Step 4 while i <= N, (N is the size of the Array)
4. Check if array[i] == value  
    if true, set 'position' to 'i'
    break out of the loop
    [Loop ends]
5. If 'position' == -1
    print "value not found in the array"
   Else
    print "value found at " 'position'
6. Exit.
```
___  

## Example

Suppose that we have an array on `int` (integers) named `numbers`.
 We have `10` elements in the `numebers` array.
  The values might be `random` or input by a user, but it would not affect
the execution of our linear search algorithm.
```java
class LinearSearch {
    public static void main(String[] args) {
        // create an array of integers, with 10 elements, named 'numbers'
        int[] numbers = {10, 8, 2, 7, 3, 4, 9, 1, 6, 5};
    }
}
```
Let us say that we have to search for the number `4` in our numbers array. Then,
- searching the `numbers` array for the value `4` means to find out whether
the value `4` is present inside the array.
- if the value `4` does exist inside the array (for this case, it does), we need
to know the position (index) where the value was found.
- if the value is not present in the array, then we simply wish to notify the user
about the same.

___

## Comparison of the two searches

### GIF 1
![comparison of the two techniques](https://www.mathwarehouse.com/programming/images/binary-vs-linear-search/binary-and-linear-search-animations.gif)  
`Sequential search` is just another name for `linear search`

___

### GIF 2 Best Case Scenario
![best case scenario](https://www.mathwarehouse.com/programming/images/binary-vs-linear-search/linear-vs-binary-search-best-case.gif)

___

### GIF 3 Worst Case Scenario
![worst case scenario](https://www.mathwarehouse.com/programming/images/binary-vs-linear-search/linear-vs-binary-search-worst-case.gif)

___
