# Map in JS

Here’s a list of common Map methods and properties in JavaScript, along with one-line explanations:

## Properties:

1. size:
   Explanation: Returns the number of key-value pairs in the Map.

## Methods:

1. set(key, value):

   Explanation: Adds a new key-value pair to the Map, or updates the value if the key already exists, and returns the Map.

2. get(key):

   Explanation: Returns the value associated with the specified key, or undefined if the key does not exist.

3. has(key):

   Explanation: Returns true if the Map contains the specified key, otherwise returns false.

4. delete(key):

   Explanation: Removes the key-value pair associated with the specified key from the Map, and returns true if the pair was removed, otherwise returns false.

5. clear():

   Explanation: Removes all key-value pairs from the Map, leaving it empty.

6. keys():

   Explanation: Returns a new Iterator object that contains the keys of the Map.

7. values():

   Explanation: Returns a new Iterator object that contains the values of the Map.

8. entries():

   Explanation: Returns a new Iterator object that contains an array of [key, value] pairs for each element in the Map.

9. forEach(callbackFn, thisArg):

   Explanation: Executes a provided function once for each key-value pair in the Map, with the optional thisArg as the this context.

   ```javascript
   // Create a new Map
   const myMap = new Map([
     ["name", "Bob"],
     ["age", 25],
   ]);

   // Define an object with a method to use as the callback
   const context = {
     prefix: "Entry:",
     log(value, key) {
       console.log(`${this.prefix} Key: ${key}, Value: ${value}`);
     },
   };

   // Use forEach with the callback function and context
   myMap.forEach(function (value, key) {
     this.log(value, key);
   }, context);

   // Output:
   // Entry: Key: name, Value: Bob
   // Entry: Key: age, Value: 25
   ```

10. `[Symbol.iterator]()`:

    Explanation: Returns an iterator object that iterates over the [key, value] pairs in the Map, allowing the Map to be used in for...of loops and other iterable contexts.

    ```javascript
    // Create a new Map and add some key-value pairs
    const myMap = new Map();
    myMap.set("name", "Alice");
    myMap.set("age", 30);
    myMap.set("city", "New York");

    // Use the [Symbol.iterator]() to iterate over the Map
    for (const [key, value] of myMap) {
      console.log(`${key}: ${value}`);
    }

    // Output:
    // name: Alice
    // age: 30
    // city: New York
    ```
