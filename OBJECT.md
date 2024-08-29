# Object in JS

Here's a list of common object methods and properties in JavaScript, along with one-line explanations:

## Properties:

1. constructor:

   Explanation: Returns the function that created the instance's prototype (usually the constructor function for the object).

   ```javascript
   // Define a constructor function
   function Person(name, age) {
     this.name = name;
     this.age = age;
   }

   // Create an instance of Person
   let person1 = new Person("Alice", 30);

   // Access the constructor property
   console.log(person1.constructor);
   // Output: [Function: Person]

   // Check if the constructor is Person
   console.log(person1.constructor === Person);
   // Output: true

   // Create an instance of a built-in object
   let array = [1, 2, 3];

   // Access the constructor property of the array
   console.log(array.constructor);
   // Output: [Function: Array]

   // Check if the constructor is Array
   console.log(array.constructor === Array);
   // Output: true
   ```

2. prototype:

   Explanation: Returns the prototype object of a constructor function (can be used to add methods to all instances of that constructor).

   ```javascript
   // Constructor function for creating Person objects
   function Person(firstName, lastName) {
     this.firstName = firstName;
     this.lastName = lastName;
   }

   // Adding a method to the prototype
   Person.prototype.getFullName = function () {
     return this.firstName + " " + this.lastName;
   };

   // Adding a property to the prototype
   Person.prototype.nationality = "Indian";

   // Creating instances of Person
   let person1 = new Person("John", "Doe");
   let person2 = new Person("Jane", "Smith");

   // Using the method from the prototype
   console.log(person1.getFullName()); // Output: John Doe
   console.log(person2.getFullName()); // Output: Jane Smith

   // Accessing the prototype property
   console.log(person1.nationality); // Output: Indian
   console.log(person2.nationality); // Output: Indian

   // Modifying the prototype property affects all instances
   Person.prototype.nationality = "American";

   console.log(person1.nationality); // Output: American
   console.log(person2.nationality); // Output: American
   ```

3. `__proto__`:

   Explanation: Accesses the internal prototype of the object (deprecated, use Object.getPrototypeOf() instead).

   ```javascript
   // Create a prototype object
   let animal = {
     eats: true,
     walk() {
       console.log("Animal is walking");
     },
   };

   // Create a new object with animal as its prototype
   let rabbit = {
     jumps: true,
   };

   rabbit.__proto__ = animal; // Set animal as the prototype of rabbit

   // Now rabbit can access properties and methods from animal
   console.log(rabbit.eats); // Output: true
   rabbit.walk(); // Output: Animal is walking

   // You can also verify the prototype
   console.log(rabbit.__proto__ === animal); // Output: true

   // You can add new properties to the prototype
   rabbit.__proto__.sleep = function () {
     console.log("Animal is sleeping");
   };

   rabbit.sleep(); // Output: Animal is sleeping
   ```

4. hasOwnProperty(property):

   Explanation: Returns true if the object has the specified property as its own property, not inherited.

   ```javascript
   // Create an object with some properties
   let person = {
     name: "Alice",
     age: 30,
     city: "New York",
   };

   // Check if the 'name' property exists in the object
   console.log(person.hasOwnProperty("name")); // Output: true

   // Check if the 'gender' property exists in the object
   console.log(person.hasOwnProperty("gender")); // Output: false

   // Check if the 'toString' property exists in the object (inherited from prototype)
   console.log(person.hasOwnProperty("toString")); // Output: false
   ```

5. isPrototypeOf(object):

   Explanation: Returns true if the object is in the prototype chain of the specified object.

   ```javascript
   // Define a constructor function
   function Person(name) {
     this.name = name;
   }

   // Create an instance of Person
   let person1 = new Person("Alice");

   // Create another object that inherits from person1
   let employee = Object.create(person1);

   // Check if person1 is in the prototype chain of employee
   console.log(Person.prototype.isPrototypeOf(person1)); // Output: true

   console.log(person1.isPrototypeOf(employee)); // Output: true

   // Check if employee is in the prototype chain of person1
   console.log(employee.isPrototypeOf(person1)); // Output: false
   ```

6. toString():

   Explanation: Returns a string representing the object (usually "[object Object]").

   ```javascript
   // Define a simple object
   let person = {
     firstName: "John",
     lastName: "Doe",
     age: 30,

     // Override the toString method
     toString: function () {
       return `${this.firstName} ${this.lastName}, Age: ${this.age}`;
     },
   };

   // Using toString explicitly
   console.log(person.toString()); // Output: "John Doe, Age: 30"

   // toString is also called implicitly when an object is coerced to a string
   console.log(String(person)); // Output: "John Doe, Age: 30"
   ```

7. valueOf():

   Explanation: Returns the primitive value of the specified object (same as toString() for objects).

## Methods:

1. Object.assign(target, ...sources):

   Explanation: Copies the values of all enumerable properties from one or more source objects to a target object and returns the target object.

   ```javascript
   // Source objects
   const source1 = { a: 1, b: 2 };
   const source2 = { c: 3, d: 4 };

   // Target object
   const target = { a: 0 };

   // Use Object.assign to copy properties from source1 and source2 to the target object
   //If there are properties with the same key in multiple source objects, the last source object’s value will overwrite the previous values.
   Object.assign(target, source1, source2);

   console.log(target);
   // Output: { a: 1, b: 2, c: 3, d: 4 }
   ```

2. Object.create(prototype, propertiesObject):

   Explanation: Creates a new object with the specified prototype object and properties.

   ```javascript
   // Define a prototype object
   const prototypeObject = {
     greet() {
       return `Hello, my name is ${this.name}`;
     },
   };

   // Define property descriptors for the new object
   const properties = {
     name: {
       value: "Alice",
       writable: true, // Can be modified
       enumerable: true, // Shows up in for...in loops
       configurable: true, // Can be deleted or modified
     },
     age: {
       value: 30,
       writable: false, // Cannot be modified
       enumerable: true,
       configurable: true,
     },
   };

   // Create a new object with the prototypeObject and properties
   const newObject = Object.create(prototypeObject, properties);

   console.log(newObject.greet()); // Output: "Hello, my name is Alice"

   // Access properties
   console.log(newObject.name); // Output: "Alice"
   console.log(newObject.age); // Output: 30

   // Modify the properties
   newObject.name = "Bob";
   console.log(newObject.name); // Output: "Bob"

   // Attempt to modify a non-writable property
   newObject.age = 35;
   console.log(newObject.age); // Output: 30 (unchanged)
   ```

3. Object.defineProperty(obj, prop, descriptor):

   Explanation: Defines a new property or modifies an existing property on an object, and returns the object.

   ```javascript
   // Create an empty object
   let person = {};

   // Define a property 'name' with a descriptor
   Object.defineProperty(person, "name", {
     value: "John Doe",
     writable: false, // Property value cannot be changed
     enumerable: true, // Property will be listed in loops (like for...in)
     configurable: false, // Property cannot be deleted or reconfigured
   });

   console.log(person.name); // Output: John Doe

   // Attempt to modify the 'name' property
   person.name = "Jane Doe";
   console.log(person.name); // Output: John Doe (because writable is false)

   // Attempt to list properties
   for (let key in person) {
     console.log(key); // Output: name (because enumerable is true)
   }

   // Attempt to delete the 'name' property
   delete person.name;
   console.log(person.name); // Output: John Doe (because configurable is false)
   ```

4. Object.defineProperties(obj, props):

   Explanation: Defines new or modifies existing properties directly on an object, and returns the object.

   ```javascript
   // Create an empty object
   let person = {};

   // Define multiple properties on the object using Object.defineProperties
   Object.defineProperties(person, {
     name: {
       value: "John",
       writable: true,
       enumerable: true,
       configurable: true,
     },
     age: {
       value: 30,
       writable: false, // Cannot modify the value
       enumerable: true,
       configurable: true,
     },
     greet: {
       value: function () {
         console.log(
           `Hello, my name is ${this.name} and I am ${this.age} years old.`
         );
       },
       writable: true,
       enumerable: false, // Not enumerable, so it won't show up in a for...in loop or Object.keys()
       configurable: true,
     },
   });

   // Access and modify properties
   console.log(person.name); // Output: John
   person.name = "Jane";
   console.log(person.name); // Output: Jane

   console.log(person.age); // Output: 30
   person.age = 35; // This won't change the value because writable is set to false
   console.log(person.age); // Output: 30

   // Call the greet method
   person.greet(); // Output: Hello, my name is Jane and I am 30 years old.

   // List enumerable properties
   console.log(Object.keys(person)); // Output: [ 'name', 'age' ]
   ```

5. Object.entries(obj):

   Explanation: Returns an array of the object's own enumerable string-keyed property [key, value] pairs.

   ```javascript
   // Define an object
   const person = {
     name: "Alice",
     age: 30,
     occupation: "Engineer",
   };

   // Use Object.entries to get an array of [key, value] pairs
   const entries = Object.entries(person);

   console.log(entries);
   // Output: [ ['name', 'Alice'], ['age', 30], ['occupation', 'Engineer'] ]

   // Iterate over the entries
   entries.forEach(([key, value]) => {
     console.log(`${key}: ${value}`);
   });

   // Output:
   // name: Alice
   // age: 30
   // occupation: Engineer
   ```

6. Object.freeze(obj):

   Explanation: Freezes an object, preventing new properties from being added, existing properties from being removed or altered, and returns the object.

7. Object.fromEntries(entries):

   Explanation: Converts a list of key-value pairs (arrays) into an object.

   ```javascript
   // Create an array of key-value pairs
   const entries = [
     ["name", "Alice"],
     ["age", 30],
     ["job", "Engineer"],
   ];

   // Use Object.fromEntries to convert the array into an object
   const obj = Object.fromEntries(entries);

   console.log(obj);
   // Output: { name: 'Alice', age: 30, job: 'Engineer' }
   ```

8. Object.getOwnPropertyDescriptor(obj, prop):

   Explanation: Returns a property descriptor for a named property of an object.

   ```javascript
   // Define an object with various properties
   const obj = {
     name: "Alice",
     age: 30,
     greet: function () {
       return "Hello";
     },
   };

   // Add a property with specific descriptors
   Object.defineProperty(obj, "age", {
     value: 30,
     writable: false, // Property cannot be modified
     enumerable: true, // Property will appear in enumeration
     configurable: false, // Property cannot be deleted or reconfigured
   });

   // Get the property descriptor for 'age'
   const descriptor = Object.getOwnPropertyDescriptor(obj, "age");

   console.log(descriptor);
   /* Output:
   {
   value: 30,
   writable: false,
   enumerable: true,
   configurable: false
   }
   */
   ```

9. Object.getOwnPropertyDescriptors(obj):

   Explanation: Returns an object containing all own property descriptors of a given object.

   ```javascript
   // Create an object with various property descriptors
   const obj = {
     name: "Alice",
     age: 30,
   };

   // Define property descriptors for the properties
   Object.defineProperty(obj, "name", {
     value: "Alice",
     writable: false, // Cannot be changed
     enumerable: true, // Will show up in enumeration
     configurable: true, // Can be deleted or changed
   });

   Object.defineProperty(obj, "age", {
     value: 30,
     writable: true, // Can be changed
     enumerable: true, // Will show up in enumeration
     configurable: false, // Cannot be deleted or changed
   });

   // Get property descriptors for all own properties
   const descriptors = Object.getOwnPropertyDescriptors(obj);

   console.log(descriptors);

   /*
   output: {
    name: {
        value: 'Alice',
        writable: false,
        enumerable: true,
        configurable: true
    },
    age: {
        value: 30,
        writable: true,
        enumerable: true,
        configurable: false
    }
   }
   */
   ```

10. Object.getOwnPropertyNames(obj):

    Explanation: Returns an array of all own property names (including non-enumerable properties) of a given object.

11. Object.getPrototypeOf(obj):

    Explanation: Returns the prototype of the specified object.

12. Object.is(value1, value2):

    Explanation: Determines whether two values are the same value (similar to ===, but with special handling for NaN and -0).

    ```javascript
    // Example 1: Comparing two identical values
    console.log(Object.is(5, 5)); // Output: true

    // Example 2: Comparing two different values
    console.log(Object.is("hello", "world")); // Output: false

    // Example 3: Comparing NaN values
    console.log(Object.is(NaN, NaN)); // Output: true
    // Note: NaN is not equal to NaN using the strict equality operator (===)

    // Example 4: Comparing -0 and +0
    console.log(Object.is(-0, +0)); // Output: false
    // Note: -0 and +0 are considered equal using the strict equality operator (===)

    // Example 5: Comparing different objects
    const obj1 = { name: "Alice" };
    const obj2 = { name: "Alice" };
    console.log(Object.is(obj1, obj2)); // Output: false
    // Different object references are not considered equal
    ```

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

    ```javascript
    // Create an object with some properties
    let obj = {
      name: "Alice",
      age: 30,
      job: "Engineer",
    };

    // Check if the object has its own property 'name'
    console.log(obj.hasOwnProperty("name")); // Output: true

    // Check if the object has its own property 'age'
    console.log(obj.hasOwnProperty("age")); // Output: true

    // Check if the object has its own property 'job'
    console.log(obj.hasOwnProperty("job")); // Output: true

    // Check if the object has its own property 'salary' (which it does not have)
    console.log(obj.hasOwnProperty("salary")); // Output: false

    // Check if the object has its own property 'toString' (inherited from Object.prototype)
    console.log(obj.hasOwnProperty("toString")); // Output: false
    ```

19. Object.prototype.toString():

    Explanation: Returns a string representation of the object (usually "[object Object]").

20. Object.prototype.toLocaleString():

    Explanation: Returns a string representing the object, with localization applied.

    ```javascript
    // Create a Date object
    let date = new Date();

    // Use toLocaleString to get a locale-specific string representation of the date
    console.log(date.toLocaleString());
    // Output might be something like: "8/28/2024, 4:00:00 PM" (format varies based on locale)

    let dateOptions = {
      weekday: "long",
      year: "numeric",
      month: "long",
      day: "numeric",
    };
    console.log(date.toLocaleString("en-US", dateOptions));
    // Output: "Wednesday, August 28, 2024"

    // Object with custom properties
    let obj = {
      name: "Alice",
      age: 30,
      toLocaleString: function () {
        return `Name: ${this.name}, Age: ${this.age}`;
      },
    };

    // Use toLocaleString on the custom object
    console.log(obj.toLocaleString());
    // Output: "Name: Alice, Age: 30"
    ```
