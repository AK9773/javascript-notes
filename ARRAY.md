# Array in JS

Here's a list of common array methods and properties in JavaScript, along with one-line explanations:

## Properties

1. length:
   Explanation: Returns the number of elements in the array.

## Methods:

1. push(element):

   Explanation: Adds one or more elements to the end of an array and returns the new length of the array.

2. pop():

   Explanation: Removes the last element from an array and returns that element.

3. shift():

   Explanation: Removes the first element from an array and returns that element.

4. unshift(element):

   Explanation: Adds one or more elements to the beginning of an array and returns the new length of the array.

   ```javascript
   // Create an array of fruits
   let fruits = ["Apple", "Banana", "Cherry"];

   // Use unshift() to add a new element at the beginning of the array
   fruits.unshift("Mango");

   // Display the updated array
   console.log("Array after unshift:", fruits); // ['Mango', 'Apple', 'Banana', 'Cherry']
   ```

5. concat(array):

   Explanation: Merges two or more arrays and returns a new array without changing the original arrays.

6. slice(start, end):

   Explanation: Returns a shallow copy of a portion of an array into a new array, starting from start index up to, but not including, end index.

7. splice(start, deleteCount, item1, item2, ...):

   Explanation: Changes the contents of an array by removing, replacing, or adding elements and returns the removed elements as an array.

   ```javascript
   // Original array
   let fruits = ["Apple", "Banana", "Cherry", "Date", "Elderberry"];

   // Use splice to remove 2 elements starting from index 1
   // This will remove 'Banana' and 'Cherry'
   let removedFruits = fruits.splice(1, 2);

   console.log(fruits); // Output: ['Apple', 'Date', 'Elderberry']
   console.log(removedFruits); // Output: ['Banana', 'Cherry']

   // Use splice to add new elements at index 1
   // This will add 'Blueberry' and 'Fig' at index 1
   fruits.splice(1, 0, "Blueberry", "Fig");

   console.log(fruits); // Output: ['Apple', 'Blueberry', 'Fig', 'Date', 'Elderberry']

   // Use splice to replace elements starting from index 2
   // This will remove 'Fig' and 'Date' and add 'Grape' and 'Honeydew' at index 2
   fruits.splice(2, 2, "Grape", "Honeydew");

   console.log(fruits); // Output: ['Apple', 'Blueberry', 'Grape', 'Honeydew', 'Elderberry']
   ```

8. indexOf(element):

   Explanation: Returns the first index at which a given element can be found in the array, or -1 if it is not present.

9. lastIndexOf(element):

   Explanation: Returns the last index at which a given element can be found in the array, or -1 if it is not present.

10. includes(element):

    Explanation: Returns true if the array contains the specified element, otherwise returns false.

11. forEach(callback):

    Explanation: Executes a provided function once for each array element and returns undefined.

12. map(callback):

    Explanation: Creates a new array with the results of calling a provided function on every element in the array.

    ```javascript
    // Define an array of numbers
    const numbers = [1, 2, 3, 4, 5];

    // Use map() to create a new array where each number is doubled
    const doubledNumbers = numbers.map(function (number) {
      return number * 2;
    });

    // Output the new array
    console.log(doubledNumbers); // [2, 4, 6, 8, 10]
    ```

13. filter(callback):

    Explanation: Creates a new array with all elements that pass the test implemented by the provided function.

    ```javascript
    // Example array of numbers
    const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

    // Define a callback function that tests whether a number is even
    const isEven = (number) => number % 2 === 0;

    // Use filter to create a new array with only even numbers
    const evenNumbers = numbers.filter(isEven);

    console.log(evenNumbers); // Output: [2, 4, 6, 8, 10]
    ```

14. reduce(callback, initialValue):

    Explanation: Executes a reducer function on each element of the array, resulting in a single output value.

    ```javascript
    // Define an array of numbers
    const numbers = [1, 2, 3, 4, 5];

    // Use reduce to calculate the sum of all elements
    const sum = numbers.reduce((accumulator, currentValue) => {
      return accumulator + currentValue;
    }, 0); // Initial value is 0

    // accumulator: Holds the running total as the array is processed.
    // currentValue: Represents the current element in the array

    console.log(sum); // Output: 15
    ```

15. reduceRight(callback, initialValue):

    Explanation: Applies a function against an accumulator and each value of the array (from right to left) to reduce it to a single value.

16. find(callback):

    Explanation: Returns the first element in the array that satisfies the provided testing function, or undefined if no such element exists.

    ```javascript
    // Array of objects representing people
    const people = [
      { name: "Alice", age: 25 },
      { name: "Bob", age: 30 },
      { name: "Charlie", age: 35 },
    ];

    // Find the first person who is 30 years old
    const foundPerson = people.find((person) => person.age === 30);

    // Output the result
    console.log(foundPerson); // { name: 'Bob', age: 30 }
    ```

17. findIndex(callback):

    Explanation: Returns the index of the first element in the array that satisfies the provided testing function, or -1 if no such element exists.

    ```javascript
    // Example array of objects
    const users = [
      { id: 1, name: "Alice", age: 25 },
      { id: 2, name: "Bob", age: 30 },
      { id: 3, name: "Charlie", age: 35 },
    ];

    // Use findIndex to find the index of the first user who is over 30 years old
    const index = users.findIndex((user) => user.age > 30);

    console.log(index); // Output: 2 (index of Charlie, who is 35 years old)

    // If no user meets the condition, it returns -1
    const noUserIndex = users.findIndex((user) => user.age > 40);

    console.log(noUserIndex); // Output: -1
    ```

18. every(callback):

    Explanation: Returns true if all elements in the array pass the test implemented by the provided function, otherwise returns false.

19. some(callback):

    Explanation: Returns true if at least one element in the array passes the test implemented by the provided function, otherwise returns false.

20. sort(compareFunction):

    Explanation: Sorts the elements of an array in place and returns the sorted array.

    ```javascript
    // Example 1: Sorting numbers in ascending order
    const numbers = [10, 5, 100, 1, 25];
    numbers.sort((a, b) => a - b);
    console.log("Sorted numbers (ascending):", numbers);
    // Output: [1, 5, 10, 25, 100]

    // Example 2: Sorting numbers in descending order
    const numbersDesc = [10, 5, 100, 1, 25];
    numbersDesc.sort((a, b) => b - a);
    console.log("Sorted numbers (descending):", numbersDesc);
    // Output: [100, 25, 10, 5, 1]

    // Example 3: Sorting strings alphabetically
    const strings = ["banana", "apple", "cherry", "date"];
    strings.sort((a, b) => a.localeCompare(b));
    console.log("Sorted strings (alphabetically):", strings);
    // Output: ['apple', 'banana', 'cherry', 'date']

    // Example 4: Sorting objects by a specific property
    const objects = [
      { name: "John", age: 30 },
      { name: "Jane", age: 25 },
      { name: "Bob", age: 35 },
    ];
    objects.sort((a, b) => a.age - b.age);
    console.log("Sorted objects by age:", objects);
    // Output: [ { name: 'Jane', age: 25 }, { name: 'John', age: 30 }, { name: 'Bob', age: 35 } ]
    ```

21. reverse():

    Explanation: Reverses the order of the elements in an array in place and returns the array.

22. join(separator):

    Explanation: Joins all elements of an array into a string and returns this string, with the elements separated by the specified separator.

23. toString():

    Explanation: Returns a string representing the array and its elements, separated by commas.

24. fill(value, start, end):

    Explanation: Fills all the elements of an array from a start index to an end index with a static value and returns the modified array.

    ```javascript
    // Create an array with 5 elements, all initialized to undefined
    let arr = [1, 2, 3, 4, 5];

    // Use fill to replace all elements from index 1 to 4 (not included) with the value 0
    arr.fill(0, 1, 4);

    console.log(arr); // Output: [1, 0, 0, 0, 5]
    ```

25. copyWithin(target, start, end):

    Explanation: Shallow copies part of an array to another location in the same array and returns it without modifying its length.

    ```javascript
    // Create an array
    let array = [1, 2, 3, 4, 5, 6, 7, 8];

    // Use copyWithin to copy elements from index 2 to 5 into index 0
    // Here, we are copying the elements [3, 4, 5] to the start of the array
    let result = array.copyWithin(0, 2, 5);

    console.log(result); // Output: [3, 4, 5, 4, 5, 6, 7, 8]
    ```

26. Array of initial length and filled with a value

    ```javascript
    // Create an array of length 10 and fill it with 0s
    let array = new Array(10).fill(0);

    console.log(array); // Output: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
    ```
