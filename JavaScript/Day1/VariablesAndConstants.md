- [Variables And Constants](#Variables-And-Constants)
    - [JavaScript Variables](#JavaScript-Variables)
    - [JavaScript-Declare-Variables](#JavaScript-Declare-Variables)
    - [JavaScript var vs let](#JavaScript-var-vs-let)
    - [JavaScript Initialize Variables](#JavaScript-Initialize-Variables)
    - [Change the Value of Variables](#Change-the-Value-of-Variables)
    - [Rules for Naming JavaScript Variables](#Rules-for-Naming-JavaScript-Variables)
    - [JavaScript Constants](#JavaScript-Constants)

# Variables And Constants

## JavaScript Variables

In programming, a variable is used to store data.

**Example:**

```js
let x = 5;
```
Here, x is a variable. It's storing 10.

## JavaScript Declare Variables

In JavaScript, we use either var or let keyword to declare variables.
**Example:**

```js
var i;
let j;
```
Here i and j are variables.

## JavaScript var vs let

As we know both var and let are used to declare variables. However, there are some differences between them.

| Var         | Let |
| ----------- | ------|
| var is used in the older versions of JavaScript      | let is the new way of declaring variables starting ES6 (ES2015).       |
| var is function scoped (we will see it in later tutorials).   | let is block scoped (we will see it in later tutorials).        |

It is recommended to use let instead of var.

## JavaScript Initialize Variables

the assignment operator ```=``` to assign a value to a variable.

```
let x;
x=10;
```
Here, 10 is assigned to variable x.

You can also initialize variables during its declaration.
```
let x=10;
```
In JavaScript, it's possible to declare variables in a single statement.
``` let x = 5, y = 6, z = 7; ```

If you use a variable without initializing it, it will have an undefined value.

```
let x;
console.log(x); // undefined
```

In javaScript undefined is a special keyword. we will learn about it in later tutorials.

## Change the Value of Variables

It's possible to change the value stored in the variable.

**Example**

```
// 5 is assigned to variable x
let x = 5; 
console.log(x); // 5

// value of variable x is changed
x = 3; 
console.log(x); // 3
```

## Rules for Naming JavaScript Variables

1. Variable names must start with either a letter, an underscore _, or the dollar sign $.

**Example**
```
//valid
let a = 5;
let _a = 5;
let $a = 5;
```

2. Variable names cannot start with numbers.

**Example**
```
//invalid
let 1a=5;
```

3. JavaScript is case-sensitive. So x and X are different variables.

**Example**
```
let x = "Hello";
let X = 5;

console.log(x); // Hello
console.log(X); // 5
```

4. Keywords cannot be used as variable names. 

**Example**

```
//invalid
let new = 5; // Error! new is a keyword.
```
**Note**
In JavaScript, the variable names are generally written in camelCase if it has multiple words. For example, firstName, annualSalary, etc.

## JavaScript Constants

The const keyword was also introduced in the ES6(ES2015) version to create constants.
```
const x = 5;
```
Once a constant is initialized, we cannot change its value.
```
const x = 5;
x = 10;  // Error! constant cannot be changed.
```
Also, you cannot declare a constant without initializing it.
```
const x; // Error! Missing initializer in const declaration.
x=5; 
```



