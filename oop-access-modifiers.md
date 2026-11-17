Understanding Access Modifiers in TypeScript OOP
Introduction
Object-Oriented Programming (OOP) relies heavily on encapsulation, which is the practice of restricting direct access to an object's internal components. In TypeScript, access modifiers play a crucial role in achieving encapsulation by controlling the visibility and accessibility of properties and methods within classes.

What are Access Modifiers?
Access modifiers are keyword labels applied to class properties and methods that define where they can be accessed from. TypeScript provides three main access modifiers out-of-the-box, along with a special readonly keyword to protect data integrity.

The Four Types of Modifiers
1. Public
By default, all class members in TypeScript are public. They can be accessed freely from anywhere—inside the class, by its subclasses, or outside the class via an instance.


class Vehicle {
    public brand: string;
    constructor(brand: string) {
        this.brand = brand;
    }
}

2. Private
A private member cannot be accessed from outside its containing class, not even by subclasses. It is strictly limited to the class where it is defined.


class BankAccount {
    private balance: number = 1000;
    public getBalance(): number {
        return this.balance;
    }
}

3. Protected
protected members are similar to private ones, but with one key difference: they can be accessed within subclasses, making them ideal for inheritance hierarchies.


class Employee {
    protected baseSalary: number = 50000;
}

class Manager extends Employee {
    getSalary(): number {
        return this.baseSalary; // Accessible because it's protected
    }
}

4. Readonly
The readonly modifier prevents a property from being modified after the object has been initialized in the constructor, ensuring immutability.

class User {
    readonly id: number;
    constructor(id: number) {
        this.id = id;
    }
}

Conclusion
Access modifiers are fundamental building blocks for writing secure, maintainable, and robust TypeScript code. By properly utilizing public, private, protected, and readonly keywords, developers can successfully hide internal logic and enforce clean class-based architectures.