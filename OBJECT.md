# Object in JS

Here's a list of common object methods and properties in JavaScript, along with one-line explanations:

## Properties:

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

## Methods:

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
