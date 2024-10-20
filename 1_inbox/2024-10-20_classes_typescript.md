---
date: 2024-10-20 
tags: 
    - typescript
hubs: 
    -   "[[2024-10-20_typescript-basics|typescript basics]]"
---

# classes_typescript
essenzialmente worka come java cambia solo la sintassi

## basic syntax
```javascript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    greet(): string {
        return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
    }
}
```

## create an instance
```javascript
let person1 = new Person("John", 30);
console.log(person1.greet()); // Output: "Hello, my name is John and I am 30 years old."
```

## Access modifiers
- public (can be accessed from everywhere)
- private (can be accessed only in the class iteself)
- protected (can be accessed in the calls and subclasses)
- readonly (can only be assigned once)

## Inheritance
```javascript
class Animal {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    makeSound(): void {
        console.log("Animal sound");
    }
}

class Dog extends Animal {
    breed: string;

    constructor(name: string, breed: string) {
        super(name); // Calls the parent class constructor
        this.breed = breed;
    }

    makeSound(): void {
        console.log("Woof!"); // Overrides the parent method
    }
}

let myDog = new Dog("Buddy", "Golden Retriever");
myDog.makeSound(); // Output: "Woof!"
```

## Abstract class
```javascript
abstract class Shape {
    abstract area(): number; // Abstract method to be implemented by subclasses

    printArea(): void {
        console.log(this.area());
    }
}

class Circle extends Shape {
    radius: number;

    constructor(radius: number) {
        super();
        this.radius = radius;
    }

    area(): number {
        return Math.PI * this.radius ** 2; // Implements the abstract method
    }
}

let myCircle = new Circle(5);
myCircle.printArea(); // Output: 78.53981633974483
```

## Static methods
```javascript
class Calculator {
    static add(a: number, b: number): number {
        return a + b;
    }
}

console.log(Calculator.add(5, 10)); // Output: 15
```

## Classes with interface
```javascript
interface Drivable {
    drive(): void;
}

class Car implements Drivable {
    drive(): void {
        console.log("The car is driving.");
    }
}

let myCar = new Car();
myCar.drive(); // Output: "The car is driving."
```
