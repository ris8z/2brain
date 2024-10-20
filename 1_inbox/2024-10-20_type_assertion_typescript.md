---
date: 2024-10-20 
tags: 
    - typescript
hubs: 
    -   "[[2024-10-20_typescript-basics|typescript basics]]"
---

# type_assertion_typescript

## Definition 

Type assertion is a way to tell (tsc) what type you expect.
You can think of them as type "casts" in other languages. (but they are not changeing the type)

## Syntax :

There are two ways to write a type assertion:

1. Angle-bracket syntax:
```javascript
let someValue: any = "this is a string";
let strLength: number = (<string>someValue).length;

```
2. as syntax (preferred in JSX and modern TypeScript):
```javascript
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
```

## Key Use Cases for Type Assertions:

1. When you have a value of a general type like **any**: If a variable is typed as any, TypeScript has no knowledge of its structure. Type assertions can help you tell the compiler what type it actually is.
```javascript
let someValue: any = "hello world";
let strLength: number = (someValue as string).length;
```

2. Narrowing down types in **unions**: If a value can be of multiple types (via union types), a type assertion can be used to "narrow" it down to a specific type.
```javascript
function getArea(shape: string | number): number {
    if (typeof shape === "string") {
        return (shape as string).length; // assuming string length as area for this example
    } else {
        return (shape as number) * (shape as number); // square calculation for numbers
    }
}
```
3. When working with **DOM elements**: TypeScript does not know the specific type of an element returned by document.getElementById(), so you can use a type assertion to specify it.
```javascript
let inputElement = document.getElementById("input-field") as HTMLInputElement;
inputElement.value = "Hello!";
```
----------

> [!IMPORTANT]
> Type assertions do not perform type conversion. They only tell TypeScript to treat a value as a specific type at compile time.
```javascript
let numberString: any = "123";
let numberValue: number = numberString as number; // This does NOT convert "123" into the number 123, it just tells TypeScript to treat it as a number.

//Avoid unnecessary assertions: Type assertions should be used with caution and only when you are confident about the type.
```
