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

### Complexity of Linear Search Algorithm

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

### Sample code for searching in a non-primitive array using linear search

```java
public class LinearSearchNP {
    public static void main(String[] args) {
    
            int n = 10;
    
            Student[] students = new Student[n];
    
            fillStudentValues(students);
    
            displayClass(students);
    
            int value = 0;
    
            int pos = -1;
    
            pos = linearSearch(students, value);
    
            if (pos == -1) {
                System.out.println("No student got " + value + " marks.");
            } else {
                System.out.println(students[pos].getName() + " got " + value + " marks.");
            }
    
        }
    
        private static int linearSearch(Student[] students, int value) {
            int pos = -1 ;
            for (int i = 0; i < students.length; i++) {
                if (students[i].getMarks() == value) {
                    pos = i;
                    break;
                }
            }
            return pos;
        }
    
        private static void displayClass(Student[] students) {
            for (Student student : students) {
                if (student != null) {
                    System.out.println(student);
                }
            }
        }
    
        private static void fillStudentValues(Student[] students) {
            for (int i = 0; i < students.length; i++) {
                students[i] = new Student();
                int randomNum = (int) (Math.random() * 10);
                students[i].setMarks(randomNum);
                students[i].setName("Student " + (i + 1));
            }
        }
    }
    class Student {
        private String name;
        private int marks;
    
        public String getName() {
            return name;
        }
    
        public void setName(String name) {
            this.name = name;
        }
    
        public int getMarks() {
            return marks;
        }
    
        public void setMarks(int marks) {
            this.marks = marks;
        }
    
        @Override
        public String toString() {
            return ("(" + this.marks + ", " + this.name + ")");
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

### Example

Suppose that we have an array of `int` (integers) named `numbers`.
 We have `10` elements in the `numebers` array.
  The values might be `random` or input by a user, but it would not affect
the execution of our linear search algorithm.
```java
class BinarySearch {
    public static void main(String[] args) {
        // create an array of integers, with 10 elements, named 'numbers'
        int[] numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
        // it is compulsory for the algorithm to have a sorted array
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
- for this array, the `beg` is `index 0`, `end` is `index 9` and mid is `index 4`  
`(0 + 9) / 2 = 4.5 -> 4`
- the above values will change after the first iteration, according to condition  
`array[mid] == value || array[mid] > value || array[mid] < value` 

___

### Complexity of Binary Search Algorithm

The Binary Search Algorithm takes `O(log n)` time, where `n` is the number of elements in the array.
The complexity is calculated depending on the number of comparisons done.
With each comparison, the size of the segment which we have to search is reduced to half. 
___

### Sample code for searching a value in an integer array (binary search)

```java
public class BinarySearch {

    public static void main(String[] args) {

        int n = 10;

        int[] numbers = new int[n];

//        fill values for the numbers array

        fillValues(numbers);

//        print the elements of the array on screen
        print(numbers);

//        search for the number 4
        int index = binarySearch(numbers, 4);

        if (index == -1) {
            System.out.println("Element not found");
        } else {
            System.out.println("Element found at index: " + index);
        }

    }

    //    method to initialize the elements of the array
    private static void fillValues(int[] array) {

//        travers the array
        for (int i = 0; i < array.length; i++) {

//            set the elements to a value
            array[i] = i + 1;   //  this way, the values will be sorted
        }

    }


    // method to print the elements of an array
    private static void print(int[] array) {
        for (int i = 0; i < array.length; i++) {
            System.out.println("i : " + i + ", value :" + array[i]);
        }
    }

    // method to search for a value in the array (binary)
    private static int binarySearch(int[] array, int value) {

        int beg, end, mid;
        beg = 0;
        end = array.length - 1;
        int pos = -1;

        while (beg <= end) {

            mid = (beg + end) / 2;

            if (array[mid] == value) {  //  if value is present at the mid of the array

                pos = mid;
                break;

            } else if (array[mid] > value) {

                end = mid - 1;

            } else {

                beg = mid + 1;

            }

        }

        return pos;
    }

}
```

### Sample code for searching in an object (non-primitive) array using Binary Search

```java
package practice;

public class BinarySearchNP {

    public static void main(String[] args) {

        int n = 10;

        Student[] students = new Student[n];

        fillStudents(students);

        displayClass(students);

        int beg = 0, end = students.length - 1 , mid, pos = -1;

        int value = 45;

        while (beg <= end) {
            mid = (beg + end) / 2;

            if (students[mid].getRollNo() == value) {
                pos = mid;
                break;
            } else if (students[mid].getRollNo() > value) {
                end = mid - 1;
            } else {
                beg = mid + 1;
            }



        }

        if (pos == -1) {
            System.out.println(value + " not found");
        } else {
            System.out.println(value + " found at index: " + pos);
        }



    }

    private static void displayClass(Student[] students) {
        for (Student student : students) {
            if (student != null) {
                System.out.println(student);
            }
        }
    }

    private static void fillStudents(Student[] students) {
        for (int i = 0; i < students.length; i++) {
            students[i] = new Student();
            students[i].setRollNo(i + 1);
            students[i].setName("Student " + (i + 1));
        }
    }
}
class Student {
    private String name;
    private int rollNo;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getRollNo() {
        return rollNo;
    }

    public void setRollNo(int rollNo) {
        this.rollNo = rollNo;
    }

    @Override
    public String toString() {
        return ("(" + this.rollNo + ", " + this.name + ")");
    }
}
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

### Help Links

1. [Linear Search, Wikipedia](https://en.wikipedia.org/wiki/Linear_search) & [Linear Search, Wikipedia Talk](https://en.wikipedia.org/wiki/Talk%3ALinear_search)
2. [Binary Search, Wikipedia](https://en.wikipedia.org/wiki/Binary_search_algorithm)