Blog 1  
Q1: What are some differences between interfaces and types in TypeScript?

**Interface:**
An interface is like a blueprint in TypeScript. It defines what properties and methods an object should have.

Interfaces are best for objects, mainly used to define the shape of objects and classes.

Interfaces can be extended — one interface can extend multiple interfaces to build larger structures.

Interfaces can be re-declared — TypeScript automatically merges them.

Interfaces can be easily implemented by classes.

In large codebases, interfaces often perform slightly better during compilation.

Example : 

```
interface Person {
  name: string;
  age: number;
  greet(): void;
}

class Student implements Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const student = new Student("Alice", 21);
student.greet();  // Output: Hello, my name is Alice
```

**Type:**
In TypeScript, a type is a way to define a custom name for a specific structure.

Types are more flexible — they can define not only objects, but also functions, unions, intersections, and tuples.

Types cannot be extended like interfaces — instead, they use intersection (&) to combine structures.

Types cannot be re-declared — declaring the same type name more than once causes an error.

Types cannot be directly implemented by a class (unless the type represents an object shape).

Types support advanced features like mapped types and conditional types.

Example :


```
type Status = "loading" | "success" | "error";

function showStatus(status: Status): void {
  console.log(`Status: ${status}`);
}

showStatus("loading");  // Output: Status: loading
showStatus("success");  // Output: Status: success
```

