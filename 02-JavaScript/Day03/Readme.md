- [Conditionals](#conditionals)
	- [If](#if)
	- [If Else](#if-else)
	- [If  Else if Else](#if--else-if-else)
	- [Switch](#switch)
	- [Ternary Operators](#ternary-operators)
- [Excercise](#exercise)

# Conditionals

Conditional statements are used for  make decisions based on different conditions.
By default , statements in JavaScript script executed sequentially from top to bottom. If the processing logic require so, the sequential flow of execution can be altered in two ways:

- Conditional execution: a block of one or more statements will be executed if a certain expression is true
- Repetitive execution: a block of one or more statements will be repetitively executed as long as a certain expression is true. In this section, we will cover _if_, _else_ , _else if_ statements. The comparison and logical operators we learned in the previous sections will be useful in here.

Conditions can be implementing using the following ways:

- if
- if else
- if else if else
- switch
- ternary operator

## If

In JavaScript and other programming languages the key word _if_ is to used check if a condition is true and to execute the block code. To create an if condition, we need _if_ keyword, condition inside a parenthesis and block of code inside a curly bracket({}).

```js
// syntax
if (condition) {
  //this part of code runs for truthy condition
}
```

**Example:**

```js
let num = 3
if (num > 0) {
  console.log(`${num} is a positive number`)
}
//  3 is a positive number
```

As you can see in the  condition example above, 3 is greater than 0, so it is a positive number. The condition was true and the block of code was executed. However, if the condition is false, we won't  see any results.

```js
let isRaining = true
if (isRaining) {
  console.log('Remember to take your rain coat.')
}
```

 The same goes for the second condition, if isRaining is false the if block will not be executed and we do not see any output. In order to see the result of a falsy condition, we should have another block, which is going to be _else_.

## If Else

If condition is true the first block will be executed, if not the else condition will be executed.

```js
// syntax
if (condition) {
  // this part of code runs for truthy condition
} else {
  // this part of code runs for false condition
}
```

```js
let num = 3
if (num > 0) {
  console.log(`${num} is a positive number`)
} else {
  console.log(`${num} is a negative number`)
}
//  3 is a positive number

num = -3
if (num > 0) {
  console.log(`${num} is a positive number`)
} else {
  console.log(`${num} is a negative number`)
}
//  -3 is a negative number
```

The last condition is false, therefore the else block was executed. What if we have more than two conditions? In that case,  we would use *else if* conditions.

## If  Else if Else

On our daily life, we make decisions on daily basis. We make decisions not by checking  one or two conditions instead we make decisions based on multiple conditions. As similar to our daily life, programming is also full of conditions. We use *else if* when we have multiple conditions.

```js
// syntax
if (condition) {
     // code
} else if (condition) {
   // code
} else {
    //  code

}
```

**Example:**

```js
let a = 0
if (a > 0) {
  console.log(`${a} is a positive number`)
} else if (a < 0) {
  console.log(`${a} is a negative number`)
} else if (a == 0) {
  console.log(`${a} is zero`)
} else {
  console.log(`${a} is not a number`)
}
```

## Switch

Switch  is an alternative for **if else if else else**.
The switch statement starts with a *switch* keyword followed by a parenthesis and code block. Inside the code block we will have different cases. Case block runs if the value in the switch statement parenthesis matches with the case value. The break statement is to terminate execution so the code execution  does not go down after the condition is satisfied.  The default block runs if all the cases don't satisfy the condition.

```js
switch(caseValue){
  case 1:
    // code
    break
  case 2:
   // code
   break
  case 3:
   // code
   break
  default:
   // code
}
```

```js
let weather = 'cloudy'
switch (weather) {
  case 'rainy':
    console.log('You need a rain coat.')
    break
  case 'cloudy':
    console.log('It might be cold, you need a jacket.')
    break
  case 'sunny':
    console.log('Go out freely.')
    break
  default:
    console.log(' No need for rain coat.')
}
```
// Examples to use conditions in the cases

```js
let num = prompt('Enter number');
switch (true) {
  case num > 0:
    console.log('Number is positive');
    break;
  case num == 0:
    console.log('Numbers is zero');
    break;
  case num < 0:
    console.log('Number is negative');
    break;
  default:
    console.log('Entered value was not a number');
}
```

## Ternary Operators

Another way to write conditionals is using ternary operators. We have covered this in other sections, but we should also mention it here.

```js
let isRaining = true
isRaining
  ? console.log('You need a rain coat.')
  : console.log('No need for a rain coat.')
```

More Examples - https://www.programiz.com/javascript/ternary-operator

# Exercise

1. [Use Conditional Logic with If Statements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-conditional-logic-with-if-statements)

2. [Comparison with the Equality Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-equality-operator)

3. [Comparison with the Strict Equality Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-strict-equality-operator)

4. [Practice comparing different values](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/practice-comparing-different-values)

5. [Comparison with the Inequality Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-inequality-operator)

6. [Comparison with the Strict Inequality Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-strict-inequality-operator)

7. [Comparison with the Greater Than Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-greater-than-operator)

8. [Comparison with the Greater Than Or Equal To Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-greater-than-or-equal-to-operator)

9. [Comparison with the Less Than Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-less-than-operator)

10. [Comparison with the Less Than Or Equal To Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-less-than-or-equal-to-operator)

11. [Comparisons with the Logical And Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparisons-with-the-logical-and-operator)

12. [Comparisons with the Logical Or Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/comparisons-with-the-logical-or-operator)

13. [Introducing Else Statements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/introducing-else-statements)

14. [Introducing Else If Statements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/introducing-else-if-statements)

15. [Logical Order in If Else Statements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/logical-order-in-if-else-statements)

16. [Chaining If Else Statements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/chaining-if-else-statements)

17. [Selecting from Many Options with Switch Statements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/selecting-from-many-options-with-switch-statements)

18. [Adding a Default Option in Switch Statements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/adding-a-default-option-in-switch-statements)

19. [Multiple Identical Options in Switch Statements](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/multiple-identical-options-in-switch-statements)

20. [Replacing If Else Chains with Switch](freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/replacing-if-else-chains-with-switch)





