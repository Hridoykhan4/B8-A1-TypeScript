Understanding Type Narrowing in TypeScript
Introduction
Type narrowing is one of the most powerful features in TypeScript that allows developers to work safely with union types. By refining a general type into a more specific type within a conditional block, TypeScript helps prevent runtime errors and ensures type safety.

What is Type Narrowing?
In TypeScript, when a variable has a union type like string | number, direct operations specific to only one type can cause compilation issues. Type narrowing solves this by letting developers check the runtime value using standard JavaScript control flow constructs. TypeScript's type checker analyzes these checks and narrows down the possible types within that specific code block.

Practical Examples of Type Narrowing
1. Using the typeof Operator
The typeof operator is the most common way to narrow primitive types such as strings, numbers, booleans, and symbols.

function formatInput(input: string | number): string {
    if (typeof input === "string") {
        return input.trim().toUpperCase();
    }
    return input.toFixed(2);
}

2. Using the instanceof Operator
When working with classes and object instances, instanceof is used to check if an object inherits from a specific constructor or class.

class Admin {
    constructor(public name: string) {}
}

class Guest {
    constructor(public visitorId: number) {}
}

function printDetails(user: Admin | Guest) {
    if (user instanceof Admin) {
        console.log(`Admin Name: ${user.name}`);
    } else {
        console.log(`Guest ID: ${user.visitorId}`);
    }
}

3. Using the in Operator
The in operator helps narrow object types by checking if a specific property exists within an object.


Conclusion
Type narrowing bridges the gap between dynamic JavaScript and static TypeScript. By leveraging tools like typeof, instanceof, and the in operator, developers can write robust, flexible, and completely error-free applications with full confidence.
