---
date: 2024-10-20 
tags: 
    - typescript
hubs: 
    -   "[[2024-10-20_typescript-basics|typescript basics]]"
---

# Index Signatures & keyof Assertions

## Index Signatures 
An Index Signature in TypeScript allows you to define types for objects where the property names (keys) are not known ahead of time, but their types are known. This is useful when you want to define objects that can have any number of properties, as long as they follow a certain type pattern.

### Syntax:
```javascript
{
    [key: string]: type;
}
```
key: string: The key can be any property name (as long as it's a string or number).
type: The type of the values associated with these dynamic property names.

### Examples:
```javascript
interface StringArray {
    [index: number]: string;
}

let myArray: StringArray = {
    0: "Hello",
    1: "World"
};

console.log(myArray[0]); // Output: "Hello"
```
In this example, StringArray uses an index signature to specify that its properties (or keys) are numbers, and their values are strings.

----------
```javascript
interface StringMap {
    [key: string]: string;
}

let myObject: StringMap = {
    "name": "John",
    "city": "New York",
};

console.log(myObject["name"]); // Output: "John"
```
Here, StringMap is an object where all keys must be strings and all values must be strings.


### Key Points About Index Signatures:

- The index can be either a string or number.
- The value can be any type.
- It's useful when you don't know the exact property names in advance but need to enforce a consistent value type across properties.

## Keyof Assertion

The keyof keyword in TypeScript is used to obtain the keys of an object type as a union of string literal types. It's helpful for working with types and objects more flexibly, allowing for dynamic access to properties.

### Examples
```javascript
interface Person {
    name: string;
    age: number;
    city: string;
}

type PersonKeys = keyof Person; // 'name' | 'age' | 'city'
```

In this example, keyof Person results in the union type 'name' | 'age' | 'city', representing the keys of the Person interface.

----------
```javascript
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
    return obj[key];
}

let person: Person = { name: "Alice", age: 25, city: "Paris" };
let personName = getProperty(person, "name"); // Allowed, returns 'Alice'
let personAge = getProperty(person, "age");   // Allowed, returns 25
```
In this example:

- K extends keyof T ensures that the key parameter must be one of the keys of the object T.
- The function returns the value of the specified property, ensuring type safety.


## Combining Index Signatures with keyof

You can combine index signatures and keyof for more advanced use cases, especially when dynamically accessing object properties.
```javascript
interface Person {
    name: string;
    age: number;
    [key: string]: string | number; // Index signature
}

function getProp(obj: Person, key: keyof Person) {
    return obj[key]; // Safely access property
}

let person: Person = { name: "John", age: 30, city: "New York" };
console.log(getProp(person, "name")); // Output: "John"
console.log(getProp(person, "age"));  // Output: 30
```

## Summary
- Index Signatures allow you to define dynamic property keys with specified value types, useful when working with objects with unknown or dynamic keys.
- keyof Assertions allow you to extract the keys of an object type as a union of literal string types. This is useful for enforcing type safety when accessing object properties dynamically.
- Combined Usage: keyof can be used with index signatures to create safe, dynamic property access methods or functions.
