# String in JS

Here's a list of common string methods and properties in JavaScript, along with one-line explanations:

## Properties:

1. length:

   Explanation: Returns the length of the string (number of characters).

## Methods:

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
