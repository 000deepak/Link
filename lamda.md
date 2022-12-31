# JavaScript ES6 Basics

> *Click &#9733; if you like the project. Your contributions are heartily ♡ welcome.*
<br/>

## Related Interview Questions

* [JavaScript Interview Questions](https://github.com/learning-zone/javascript-interview-questions)
* [JavaScript Design Patterns](https://github.com/learning-zone/JavaScript-Design-Patterns)
* [JavaScript Coding Practice](https://github.com/learning-zone/JavaScript-Coding-Practice)

<br/>

## Table of Contents

* [Introduction](#-1-introduction)
* ES6 New Features
    * [let](#-21-let)
    * [let vs var](#-22-let-vs-var)
    * [const](#-23-const)
    * [Arrow Function](#-24-arrow-function)
    * [Default Function Parameters](#-25-default-function-parameters)
    * [Rest Parameter](#-26-rest-parameter)
    * [Spread Operator](#-27-spread-operator)
    * [for…of](#-28-forof)
    * [Binary and Octal literals](#-29-binary-and-octal-literals)
    * [Template literals](#-210-template-literals)
    * [Enhanced Object literals](#-211-Enhanced-object-literals)
* Destructuring
    * [Array Destructuring](#-31-array-destructuring)
    * [Object Destructuring](#-32-object-destructuring)
* ES6 Modules
    * [ES6 modules](#-4-es6-modules)
* ES6 Classes
    * [Classes](#-51-classes)
    * [Getters and Setters](#-52-getters-and-setters)
    * [Class Expression](#-53-class-expression)
    * [Static methods](#-54-static-methods)
    * [Static Properties](#-55-static-properties)
    * [Computed property](#-56-computed-property)
    * [Inheritance](#-57-inheritance)
    * [new.target](#-58-newtarget)
* Symbol
    * [Symbol](#-6-symbol)
* Iterators & Generators
    * [Iterators](#-71-iterators)
    * [Generators](#-72-generators)
    * [yield](#-73-yield)
* Promises
    * [Promises](#-81-promises)
    * [Promise chaining](#-82-promise-chaining)
    * [Promise.all()](#-83-promiseall)
    * [Promise.race()](#-84-promiserace)
    * [Promise Error Handling](#-85-promise-error-handling)
* ES6 Collections
    * [Set](#-91-set)
    * [Weakset](#-92-weakset)
    * [Map](#-93-map)
    * [Weakmap](#-94-weakmap)
* Array Extensions
    * [Array.of()](#-101-arrayof)
    * [Array.from()](#-102-arrayfrom)
    * [Array.find()](#-103-arrayfind)
    * [Array.findIndex()](#-104-arrayfindindex)
* Object Extensions
    * [Object.assign()](#-111-objectassign)
    * [Object.is()](#-112-objectis)
* String Extensions
    * [String.startsWith()](#-121-stringstartswith)
    * [String.endsWith()](#-122-stringendswith)
    * [String.includes()](#-123-stringincludes)
* Proxy & Reflection
    * [Proxy](#-131-proxies)
    * [Reflection](#-132-reflect)
* Miscellaneous Features
    * [Unicode](#-141-unicode)
    * [Proper Tail calls](#-142-proper-tail-calls)

<br/>

## # 1. Introduction

JavaScript ES6 (also known as ECMAScript 2015 or ECMAScript 6) is the newer version of JavaScript that was introduced in 2015.

ECMAScript is the standard that JavaScript programming language uses. ECMAScript provides the specification on how JavaScript programming language should work.

<div align="right">
  <b><a href="#">↥ back to top</a></b>
</div>

## # 2.1. let

ES6 provides a new way of declaring a variable by using the `let` keyword. The `let` keyword is similar to the `var` keyword, except that these variables are **blocked-scope**.

**Syntax:**

```js
let variable_name;
```

In JavaScript, blocks are denoted by curly braces `{}` , for example, the `if else`, `for`, `do while`, `while`, `try catch` and so on.

**Example:**

```js
let x = 10;
if (x === 10) {
  let x = 20;
  console.log(x); // 20:  reference x inside the block
}
console.log(x); // 10: reference at the begining of the script
// Output:
20
10
```

Because the `let` keyword declares a block-scoped variable, the `x` variable inside the `if` block is a **new variable** and it shadows the `x` variable declared at the top of the script. Therefore, the value of `x` in the console is 20.

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/es6-let-zikqqb?file=/src/index.js)**

<div align="right">
  <b><a href="#">↥ back to top</a></b>
</div>

## # 2.2. let vs var

The `var` variables belong to the global scope when you define them outside a function. When you declare a variable inside a function using the `var` keyword, the scope of the variable is local. For example:

```js
function increase() {
    var counter = 10;
}
console.log(counter); // cannot access the counter variable here
// Output
// ReferenceError: counter is not defined
```

Here, the counter variable is local to the increase() function. It cannot be accessible outside of the function.

The following example displays four numbers from 0 to 4 inside the loop and the number 5 outside the loop.

```js
for (var i = 0; i < 3; i++) {
  console.log("Inside the loop:", i);
}
console.log("Outside the loop:", i);
// Output:
Inside the loop: 0 
Inside the loop: 1 
Inside the loop: 2 
Outside the loop: 3
```

Here, the i variable is a global variable. Therefore, it can be accessed from both inside and after the for loop.

The following example uses the `let` keyword instead of the `var` keyword:

```js
for (let i = 0; i < 3; i++) {
  console.log("Inside the loop:", i);
}
console.log("Outside the loop:", i);
// Output
Inside the loop: 0
Inside the loop: 1
Inside the loop: 2
Uncaught ReferenceError: i is not defined
```

Here, the variable **i** is blocked scope. It means that the variable **i** only exists and can be accessible inside the for loop block.

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/es6-let-vs-var-yvu11z)**

<div align="right">
  <b><a href="#">↥ back to top</a></b>
</div>