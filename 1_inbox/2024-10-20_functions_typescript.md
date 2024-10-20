---
date: 2024-10-20 
tags: 
    - typescript
hubs: 
    -   "[[2024-10-20_typescript-basics|typescript basics]]"
---

# functions_typescript

## Function Declaration

A function declaration defines a function with explicitly typed parameters and return type.
```javascript
function add(a: number, b: number): number {
    return a + b;
}
```
## Function Expression

A function can also be assigned to a variable using an anonymous function (function expression).
```javascript
const subtract = function(a: number, b: number): number {
    return a - b;
};
```

## Arrow Function

Arrow functions provide a shorter syntax and are often used for inline callbacks.

```javascript
const multiply = (a: number, b: number): number => {
    return a * b;
};
```

## Optional and Default Parameters

Optional Parameter: Use ? to mark a parameter as optional.
```javascript
function greet(name?: string): string {
    return `Hello, ${name || 'stranger'}!`;
}

console.log(greet()); // Hello, stranger!
console.log(greet('Alice')); // Hello, Alice!
```

Default Parameter: You can assign a default value to a parameter.
```javascript
function greet(name: string = 'stranger'): string {
    return `Hello, ${name}!`;
}

console.log(greet()); // Hello, stranger!
console.log(greet('Alice')); // Hello, Alice!
```

## Function with Rest Parameters
You can use rest parameters (...args) to accept an arbitrary number of arguments.
```javascript
function sum(...numbers: number[]): number {
    return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```
## Function Overloading
Function overloading allows a function to have multiple signatures. 
```javascript
function getLength(value: string): number;
function getLength(value: any[]): number;
function getLength(value: any): number {
    return value.length;
}

console.log(getLength('hello')); // 5
console.log(getLength([1, 2, 3])); // 3
```

## Summary:
- Type annotations help ensure that functions accept and return the expected data types.
- Functions can have optional and default parameters.
- Rest parameters allow handling multiple arguments in a flexible way.
- Function overloading enables defining multiple ways to call a function.
