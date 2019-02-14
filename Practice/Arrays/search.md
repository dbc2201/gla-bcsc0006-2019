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

___


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

### Example

Suppose that we have an array of `int` (integers) named `numbers`.
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

### Complexity of Linear Search ALgorithm

The linear search algorithm takes `O(n)` time, where `n` is the number of elements in the array.
- The **best case** for this algorithm would be, if the element is found at the first index of the array.
Because, we only needed to compare the element once.
- The **worst case** for this algorithm would be either if the element is not present in the array or if it 
is located at the last index of the array, because we would have to traverse and compare all of the elements 
of the array.
___

### Sample code for searching a value in an integer array

```java
public class LinearSearch {

    public static void main(String[] args) {

//        initialize an integer array
        int[] numbers = new int[10];

//        fill values in the array
        fillValues(numbers);

//        print the array;
        print(numbers);

//        find the index of the value in the array
        int index = linearSearch(numbers, 4);

        if (index == -1) {
            System.out.println("Element not found");
        } else {
            System.out.println("Element found at index: " + index);
        }


    }

    // method to fill random values in an array
    private static void fillValues(int[] array) {
        for (int i = 0; i < array.length; i++) {
            array[i] = (int) ((Math.random() * 10) + 1);
        }
    }

    // method to print the elements of an array
    private static void print(int[] array) {
        for (int i = 0; i < array.length; i++) {
            System.out.println("i : " + i + ", value :" + array[i]);
        }
    }

    // method to search for a value in an array (linear)
    private static int linearSearch(int[] array, int value) {

        // algorithm step 1, set pos = -1
        int pos = -1;

        for (int i = 0; i < array.length; i++) {

            // algorithm step 4, check whether array[i] == value
            if (array[i] == value) {
                pos = i;
            }
        }
        return pos;
    }

}
```
___

## Binary Search

- Binary search is another searching algorithm to search for a value in an array.
- The binary search algorithm has a pre-requisite, the array must be sorted before searching for the value.
- This algorithm only 'looks' at the *half* of the current array at any given time.

For ex - If we were to find a name inside a telephone directory, you would most likely open a page 
from the middle of the book and look for the name on that page, if not found you would decide whether to look for the name in the first part or the second.
After choosing, you would again open a page from the middle of this portion and repeat this process unless the name is found.  

___

### Algorithm for Binary Search
```
1. Initialize 'beg' to the lower bound of array (here, 0 at first),
'end' to the upper bound of the array (here, n-1 at first), 'pos' to -1
    [Loop starts]
2. Repeat steps 3 and 4 while 'beg' <= 'end'
3. Set, 'mid' to ('beg' + 'end') / 2
4. Check whether array[mid] == value,
    if yes, set 'pos' to 'mid'
        break out of loop
    else if array[mid] > value,
        set 'end' = 'mid' - 1
    else,
        set 'beg' = 'mid' + 1
    [Loop ends]
5. Check if pos == -1
        print "value is not present in loop"
   else
        print "value found at" 'pos'
6. Exit.
```

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
