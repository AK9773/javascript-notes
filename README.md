# Java Script Notes

## Array in JS

Here's a list of common array methods and properties in JavaScript, along with one-line explanations:

### Properties

1. length:
   Explanation: Returns the number of elements in the array.

### Methods:

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

## String in JS

Here's a list of common string methods and properties in JavaScript, along with one-line explanations:

### Properties:

1. length:

   Explanation: Returns the length of the string (number of characters).

### Methods:

1.  charAt(index):

    Explanation: Returns the character at the specified index in the string.

2.  charCodeAt(index):

    Explanation: Returns the Unicode value of the character at the specified index.

3.  concat(string2, string3, ...):

    Explanation: Combines two or more strings and returns a new concatenated string.

4.  includes(substring, start):

    Explanation: Returns true if the string contains the specified substring, otherwise returns false.

5.  endsWith(substring, length):

    Explanation: Returns true if the string ends with the specified substring, otherwise returns false.

    ```javascript
    // Example string
    const str = "Hello, welcome to JavaScript!";

    // Check if the string ends with "JavaScript!" within its full length
    const result1 = str.endsWith("JavaScript!");
    console.log(result1); // Output: true

    // Check if the string ends with "welcome" within the first 13 characters
    const result2 = str.endsWith("welcome", 13);
    console.log(result2); // Output: true
    ```

6.  indexOf(substring, start):

    Explanation: Returns the index of the first occurrence of the specified substring, or -1 if not found.

    ```javascript
    // Example string
    let sentence = "The quick brown fox jumps over the lazy dog.";

    // Find the first occurrence of the substring "fox"
    let firstIndex = sentence.indexOf("fox");

    // Find the first occurrence of the substring "the" starting from index 10
    let secondIndex = sentence.indexOf("the", 10);

    console.log(`The substring "fox" is found at index: ${firstIndex}`);
    // Output: The substring "fox" is found at index: 16

    console.log(`The substring "the" is found at index: ${secondIndex}`);
    // Output: The substring "the" is found at index: 31
    ```

7.  lastIndexOf(substring, start):

    Explanation: Returns the index of the last occurrence of the specified substring, or -1 if not found.

    ```javascript
    // Example string
    let text = "Hello, welcome to the JavaScript world. JavaScript is fun!";

    // Search for the last occurrence of the substring "JavaScript"
    let lastIndex = text.lastIndexOf("JavaScript");

    // Output the result
    console.log("Last occurrence of 'JavaScript':", lastIndex); // Output: 37

    // Search for the last occurrence of the substring "JavaScript" starting from index 30
    let lastIndexFromStart = text.lastIndexOf("JavaScript", 30);

    // Output the result
    console.log(
      "Last occurrence of 'JavaScript' before index 30:",
      lastIndexFromStart
    ); // Output: 21
    ```

8.  slice(start, end):

    Explanation: Extracts a part of the string and returns it as a new string, from the start index up to, but not including, the end index.

    ```javascript
    // Example string
    let text = "Hello, world!";

    // Using slice() to extract a portion of the string
    let slicedText = text.slice(7, 12);

    console.log(slicedText); // Output: "world"
    ```

9.  substring(start, end):

    Explanation: Returns a portion of the string between the start and end indexes.

    ```javascript
    // Example string
    let text = "Hello, world!";

    // Extract a substring from index 0 to index 5 (not including index 5)
    let result = text.substring(0, 5);

    console.log(result); // Output: "Hello"

    // Extract a substring from index 7 to the end of the string
    let result2 = text.substring(7);

    console.log(result2); // Output: "world!"
    ```

10. substr(start, length):

    Explanation: Returns a portion of the string, starting at the start index, and up to the specified length of characters.

    ```javascript
    // Original string
    let str = "Hello, World!";

    // Extracting a substring starting from index 7 with a length of 5
    let result = str.substr(7, 5);

    console.log(result); // Output: "World"
    ```

11. toLowerCase():

    Explanation: Returns a new string with all characters converted to lowercase.

12. toUpperCase():

    Explanation: Returns a new string with all characters converted to uppercase.

13. trim():

    Explanation: Removes whitespace from both ends of the string and returns the trimmed string.

14.     trimStart():

    Explanation: Removes whitespace from the beginning of the string and returns the trimmed string.

15. trimEnd():

    Explanation: Removes whitespace from the end of the string and returns the trimmed string.

16. replace(searchValue, newValue):

    Explanation: Returns a new string with the first match of a pattern replaced by a new value.

17. replaceAll(searchValue, newValue):

    Explanation: Returns a new string with all matches of a pattern replaced by a new value.

18. split(separator, limit):

    Explanation: Splits a string into an array of substrings, using a specified separator, and returns the array.

    ```javascript
    // Example string
    let text = "apple,banana,cherry,dragonfruit,elderberry";

    // Split the string by commas, without limit
    let fruits = text.split(",");
    console.log(fruits);
    // Output: ["apple", "banana", "cherry", "dragonfruit", "elderberry"]

    // Split the string by commas, with a limit of 3
    let limitedFruits = text.split(",", 3);
    console.log(limitedFruits);
    // Output: ["apple", "banana", "cherry"]

    // Split the string by a different separator, with no limit
    let anotherSplit = text.split("a");
    console.log(anotherSplit);
    // Output: ["", "pple,b", "n", "n", ",cherry,dr", "gonfruit,elderberry"]
    ```

19. startsWith(substring, start):

    Explanation: Returns true if the string begins with the specified substring, otherwise returns false.

20. match(regex):

    Explanation: Executes a search for a match between a regular expression and the string, returning an array of matches or null.

    ```javascript
    // Sample string
    let text = "The rain in Spain falls mainly in the plain.";

    // Regular expression to find all occurrences of 'ain'
    let regex = /ain/g;

    // Using match() to find all matches of the regex in the string
    let matches = text.match(regex);

    // Output the result
    console.log(matches); // ["ain", "ain", "ain"]
    ```

21. matchAll(regex):

    Explanation: Returns an iterator of all results matching a string against a regular expression, including capturing groups.

    ```javascript
    // Example string
    const text =
      "The quick brown fox jumps over the lazy dog. The fox is clever.";

    // Regular expression to match the word 'fox' along with its position in the string
    const regex = /fox/g;

    // Using matchAll to find all matches
    const matches = text.matchAll(regex);

    // Converting the iterator to an array to display all matches
    for (const match of matches) {
      console.log(`Found '${match[0]}' at index ${match.index}`);
    }
    // output:
    // Found 'fox' at index 16
    // Found 'fox' at index 45
    ```

22. search(regex):

    Explanation: Executes a search for a match between a regular expression and the string, returning the index of the match or -1 if not found.

23. padStart(targetLength, padString):

    Explanation: Pads the current string from the start with a specified string until it reaches the target length and returns the resulting string.

    ```javascript
    // Original string
    let originalString = "123";

    // Padding the string to a target length of 6 with the character '0'
    let paddedString = originalString.padStart(6, "0");

    console.log(paddedString); // Output: "000123"
    ```

24. padEnd(targetLength, padString):

    Explanation: Pads the current string from the end with a specified string until it reaches the target length and returns the resulting string.

25. repeat(count):

    Explanation: Returns a new string that contains the specified number of copies of the original string.

    ```javascript
    // Define a string
    let str = "Hello! ";

    // Repeat the string 3 times
    let repeatedStr = str.repeat(3);

    // Output the result
    console.log(repeatedStr); // "Hello! Hello! Hello! "
    ```

26. localeCompare(compareString):

    Explanation: Returns a number indicating whether the string comes before, after, or is equal to another string in sort order.
    localeCompare(compareString):

    string1.localeCompare(string2): Compares string1 with string2. It returns:
    A negative number if string1 is before string2 in sort order.
    Zero if they are equal.
    A positive number if string1 is after string2.
    Locale and Sensitivity:

    string3.localeCompare(string4, 'en', { sensitivity: 'base' }): Compares string3 with string4 considering case-insensitivity and accent-insensitivity due to the options specified.
    In the first comparison, 'apple' comes before 'banana', and in the second comparison, 'résumé' and 'resume' are considered equal when ignoring accents.

27. toString():

    Explanation: Returns a string representing the specified object (in this case, the string itself).

28. valueOf():

    Explanation: Returns the primitive value of the specified string object (same as toString()).

## Object

Here's a list of common object methods and properties in JavaScript, along with one-line explanations:

### Properties:

1. constructor:

   Explanation: Returns the function that created the instance's prototype (usually the constructor function for the object).

2. prototype:

   Explanation: Returns the prototype object of a constructor function (can be used to add methods to all instances of that constructor).

3. `__proto__`:

   Explanation: Accesses the internal prototype of the object (deprecated, use Object.getPrototypeOf() instead).

4. hasOwnProperty(property):

   Explanation: Returns true if the object has the specified property as its own property, not inherited.

5. isPrototypeOf(object):

   Explanation: Returns true if the object is in the prototype chain of the specified object.

6. toString():

   Explanation: Returns a string representing the object (usually "[object Object]").

7. valueOf():

   Explanation: Returns the primitive value of the specified object (same as toString() for objects).

### Methods:

1. Object.assign(target, ...sources):

   Explanation: Copies the values of all enumerable properties from one or more source objects to a target object and returns the target object.

2. Object.create(prototype, propertiesObject):

   Explanation: Creates a new object with the specified prototype object and properties.

3. Object.defineProperty(obj, prop, descriptor):

   Explanation: Defines a new property or modifies an existing property on an object, and returns the object.

4. Object.defineProperties(obj, props):

   Explanation: Defines new or modifies existing properties directly on an object, and returns the object.

5. Object.entries(obj):

   Explanation: Returns an array of the object's own enumerable string-keyed property [key, value] pairs.

6. Object.freeze(obj):

   Explanation: Freezes an object, preventing new properties from being added, existing properties from being removed or altered, and returns the object.

7. Object.fromEntries(entries):

   Explanation: Converts a list of key-value pairs (arrays) into an object.

8. Object.getOwnPropertyDescriptor(obj, prop):

   Explanation: Returns a property descriptor for a named property of an object.

9. Object.getOwnPropertyDescriptors(obj):

   Explanation: Returns an object containing all own property descriptors of a given object.

10. Object.getOwnPropertyNames(obj):

    Explanation: Returns an array of all own property names (including non-enumerable properties) of a given object.

11. Object.getPrototypeOf(obj):

    Explanation: Returns the prototype of the specified object.

12. Object.is(value1, value2):

    Explanation: Determines whether two values are the same value (similar to ===, but with special handling for NaN and -0).

13. Object.isExtensible(obj):

    Explanation: Returns true if the object is extensible (i.e., if new properties can be added to it).

14. Object.keys(obj):

    Explanation: Returns an array of a given object's own enumerable property names.

15. Object.preventExtensions(obj):

    Explanation: Prevents new properties from being added to an object and returns the object.

16. Object.seal(obj):

    Explanation: Seals an object, preventing new properties from being added and marking all existing properties as non-configurable.

17. Object.values(obj):

    Explanation: Returns an array of a given object's own enumerable property values.

18. Object.prototype.hasOwnProperty(prop):

    Explanation: Returns true if the object has the specified property as its own property, not inherited from the prototype chain.

19. Object.prototype.toString():

    Explanation: Returns a string representation of the object (usually "[object Object]").

20. Object.prototype.toLocaleString():

    Explanation: Returns a string representing the object, with localization applied.
