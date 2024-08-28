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

5. concat(array):

   Explanation: Merges two or more arrays and returns a new array without changing the original arrays.

6. slice(start, end):

   Explanation: Returns a shallow copy of a portion of an array into a new array, starting from start index up to, but not including, end index.

7. splice(start, deleteCount, item1, item2, ...):

   Explanation: Changes the contents of an array by removing, replacing, or adding elements and returns the removed elements as an array.

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

13. filter(callback):

    Explanation: Creates a new array with all elements that pass the test implemented by the provided function.

14. reduce(callback, initialValue):

    Explanation: Executes a reducer function on each element of the array, resulting in a single output value.

15. reduceRight(callback, initialValue):

    Explanation: Applies a function against an accumulator and each value of the array (from right to left) to reduce it to a single value.

16. find(callback):

    Explanation: Returns the first element in the array that satisfies the provided testing function, or undefined if no such element exists.

17. findIndex(callback):

    Explanation: Returns the index of the first element in the array that satisfies the provided testing function, or -1 if no such element exists.

18. every(callback):

    Explanation: Returns true if all elements in the array pass the test implemented by the provided function, otherwise returns false.

19. some(callback):

    Explanation: Returns true if at least one element in the array passes the test implemented by the provided function, otherwise returns false.

20. sort(compareFunction):

    Explanation: Sorts the elements of an array in place and returns the sorted array.

21. reverse():

    Explanation: Reverses the order of the elements in an array in place and returns the array.

22. join(separator):

    Explanation: Joins all elements of an array into a string and returns this string, with the elements separated by the specified separator.

23. toString():

    Explanation: Returns a string representing the array and its elements, separated by commas.

24. fill(value, start, end):

    Explanation: Fills all the elements of an array from a start index to an end index with a static value and returns the modified array.

25. copyWithin(target, start, end):

    Explanation: Shallow copies part of an array to another location in the same array and returns it without modifying its length.

## String in JS

Here's a list of common string methods and properties in JavaScript, along with one-line explanations:

### Properties:

1. length:

   Explanation: Returns the length of the string (number of characters).

### Methods:

1. charAt(index):

   Explanation: Returns the character at the specified index in the string.

2. charCodeAt(index):

   Explanation: Returns the Unicode value of the character at the specified index.

3. concat(string2, string3, ...):

   Explanation: Combines two or more strings and returns a new concatenated string.

4. includes(substring, start):

   Explanation: Returns true if the string contains the specified substring, otherwise returns false.

5. endsWith(substring, length):

   Explanation: Returns true if the string ends with the specified substring, otherwise returns false.

6. indexOf(substring, start):

   Explanation: Returns the index of the first occurrence of the specified substring, or -1 if not found.

7. lastIndexOf(substring, start):

   Explanation: Returns the index of the last occurrence of the specified substring, or -1 if not found.

8. slice(start, end):

   Explanation: Extracts a part of the string and returns it as a new string, from the start index up to, but not including, the end index.

9. ubstring(start, end):

   Explanation: Returns a portion of the string between the start and end indexes.

10. substr(start, length):

    Explanation: Returns a portion of the string, starting at the start index, and up to the specified length of characters.

11. toLowerCase():

    Explanation: Returns a new string with all characters converted to lowercase.

12. toUpperCase():

    Explanation: Returns a new string with all characters converted to uppercase.

13. trim():

    Explanation: Removes whitespace from both ends of the string and returns the trimmed string.

14. trimStart():

    Explanation: Removes whitespace from the beginning of the string and returns the trimmed string.

15. trimEnd():

    Explanation: Removes whitespace from the end of the string and returns the trimmed string.

16. replace(searchValue, newValue):

    Explanation: Returns a new string with the first match of a pattern replaced by a new value.

17. replaceAll(searchValue, newValue):

    Explanation: Returns a new string with all matches of a pattern replaced by a new value.

18. split(separator, limit):

    Explanation: Splits a string into an array of substrings, using a specified separator, and returns the array.

19. startsWith(substring, start):

    Explanation: Returns true if the string begins with the specified substring, otherwise returns false.

20. match(regex):

    Explanation: Executes a search for a match between a regular expression and the string, returning an array of matches or null.

21. matchAll(regex):

    Explanation: Returns an iterator of all results matching a string against a regular expression, including capturing groups.

22. search(regex):

    Explanation: Executes a search for a match between a regular expression and the string, returning the index of the match or -1 if not found.

23. padStart(targetLength, padString):

    Explanation: Pads the current string from the start with a specified string until it reaches the target length and returns the resulting string.

24. padEnd(targetLength, padString):

    Explanation: Pads the current string from the end with a specified string until it reaches the target length and returns the resulting string.

25. repeat(count):

    Explanation: Returns a new string that contains the specified number of copies of the original string.

26. localeCompare(compareString):

    Explanation: Returns a number indicating whether the string comes before, after, or is equal to another string in sort order.

27. toString():

    Explanation: Returns a string representing the specified object (in this case, the string itself).

28. valueOf():

    Explanation: Returns the primitive value of the specified string object (same as toString()).

29. normalize(form):

    Explanation: Returns the Unicode Normalization Form of the string, which can be used to standardize different Unicode representations of the same character.
