---
date: 2024-10-20 
tags: 
    - typescript
hubs: 
    -   "[[2024-10-20_typescript-basics|typescript basics]]"
---

# array_and_objects_typescript

## Arrays:
An array in TypeScript is a collection of values of the same data type. 

There are two main ways to declare an array in TypeScript:
1. Using square brackets []:
```javascript
let numbers: number[] = [1, 2, 3, 4, 5];
let strings: string[] = ['apple', 'banana', 'cherry'];
```

2. Using the generic Array<Type> syntax:
```javascript
let numbers: Array<number> = [1, 2, 3, 4, 5];
let strings: Array<string> = ['apple', 'banana', 'cherry'];
```

Key Features:
- Type safety: Arrays in TypeScript are type-checked, meaning only values of the specified type can be added.
- You can perform common operations like push(), pop(), filter(), map(), etc.

Example:
```javascript
let fruits: string[] = ['apple', 'banana'];
fruits.push('orange'); // Adds a new element
console.log(fruits[0]); // Accessing the first element
```

## Objects:
An object in TypeScript is a collection of key-value pairs, where the keys are strings (or symbols) and values can be any type. 

Defining an Object:

1. Using an inline object literal:
```javascript
let person = {
    name: "John",
    age: 30
};
```

2. Using an explicit type (interface or type alias): You can define a custom type to ensure that an object has specific properties.
```javascript
interface Person {
    name: string;
    age: number;
}

let person: Person = {
    name: "John",
    age: 30
};

//Similarly, you can use type instead of interface:
type Person = {
    name: string;
    age: number;
};

let person: Person = {
    name: "John",
    age: 30
};
```

Key Features:

- Type inference: TypeScript can infer the types of object properties.
- Optional properties: You can make some properties optional using the ? operator.
- Readonly properties: You can use the readonly modifier to prevent modification of certain properties.

Example with Optional and Readonly Properties:
```javascript
interface Car {
    make: string;
    model: string;
    year: number;
    color?: string; // Optional property
    readonly vin: string; // Read-only property
}

let myCar: Car = {
    make: "Toyota",
    model: "Corolla",
    year: 2020,
    vin: "1HGBH41JXMN109186"
};

// myCar.vin = "newVin"; // Error: Cannot assign to 'vin' because it is a read-only property
```

