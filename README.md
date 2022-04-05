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
