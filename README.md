# **TypeScript 101**

## **What is TypeScript ???**

- TypeScript is an alternative to JavaScript, or called a 'superset' of Javascript.

- TypeScript allows us to use strict types.

- TypeScript supports allow the modern features of JavaScript like arrow functions, const and let.

- TypeScript also comes with it own set of additional features like generics, interfaces, tuples etc.

---

## **How to install and compile TypeScript ???**

To insall TypeScript, you will first need Node.js installed to allow the use of the _Node Package Manager (npm)_.

### **Installing TypeScript Globally**

```
npm install -g typescript
```

Browsers typically by default won't read TypeScript files and they will need to be compiled into JavaScript files. Even if the code is _EXACTLY_ the same !

### **Compiling a TypeScript file**

```
tsc <<TypeScript filename>>
```

The command above will compile a TypeScript file into a JavaScript file, with the same name.

To have the TypeScript file watched and automatically update the JavaScript file with any changes made, we can use the _'-w'_ flag.

```
tsc script.ts -w
```

---

## **Type Basics _WOW_**

TypeScript has strict typing as compared to JavaScript. Whereas in JavaScript a variable can be re-assigned a value of a different type, this will lead to a compiling error in TypeScript.

- JS Example - Variables can be re-assigned different types with no issues in JavaScript.

```
let character = 'Mario';
character = 45;
```

- TS Example - Variable CANNOT be re-assigned different type values in TypeScript.

```
let age = 32;
age = 'I am too old';  // COMPILING ERROR
```

TypeScript also allows us to set an arguement type for functions. You can do this by adding a colon and data type after the parameters in a function declaration.

Here we have a function that calculates the circumference by multiplying the diameter parameter with Pi. We have specified that we are expecting the arguement when calling the function to be a number. Any other data type will cause a compiling error.

```
const calculateCircumference = (diameter: number) => {
  return diameter * MATH.PI;
};
```

---

## **Arrays and Objects**

Similar to variables having strict data types when being assigned a value, Arrays and Objects work the same way.

An Array of strings can have a value re-assigned to another string, but cannot have a different data type like a number or a boolean. If we wanted to have an that has mixed data types, the values need to be assigned when the array is declared.

- Arrays

```
let names = ['mario', 'luigi', 'yoshi']
names[0] = 'princess peach'   // This is acceptable
names[1] = 45                 // This will flag an error, not matching data type
```

If an array is declared with mixed data types, then those data types are acceptable.

```
let mixed = ['mario', 1, 'yoshi', 2, 3]
mixed[0] = 45
mixed[1] = 'toad'   // No errors
```

The logic also applies to objects, once an object has been created with properties. The data types for those properties are strictly set and cannot be changed.

```
let person = {
  name: 'harry',
  age: 32,
  gender: 'male'
}

person.name = 'luigi'   // No errors
person.age = 'forty'    // Error, not matching data type

person = {
  name: 'harry',
  age: 32,              // Error ALL object properties must be set
}
```

---

## **Data Annotations**

With TypeScript we are able to annotate the types of our variables / functions / parameters to avoid running into issues.

Here is a simple function that adds the cost of shipping to the price. But we haven't specified the type of the parameters, which could potentially cause issues if the function is called with arguements that are strings instead of numbers.

```
const addShipping = (price, shipping) => {
  return price + shipping;
};
```

With Data Annotations - Now we have declared the parameters in our functions MUST be of type number, else the code will not compile.

```
const addShipping = (price: number, shipping: number) => {
  return price + shipping;
};
```

We can also annotate functions to declare the type the data must be returned.

```
const addShipping = (price: number, shipping: number): number => {
  return price + shipping;
};
```

---

## **Union Types**

Sometimes when declaring the types of our variables, we maybe be willing to accept multiple types. When this is the case we can assign union types.

Here we have declared a variable, but have not set a type. But perhaps, we are willing to accept this variable as either a number or a string.

```
let wooptyWoop;

```

Variable with a _number OR string_ Union type annotation.

```
let wooptyWoop: number | string = 'hello';
wooptyWoop = 10000;
```

---
