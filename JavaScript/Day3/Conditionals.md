- [Conditionals](#conditionals)
	- [If](#if)
	- [If Else](#if-else)
	- [If  Else if Else](#if--else-if-else)
	- [Switch](#switch)
	- [Ternary Operators](#ternary-operators)
- [Loops](#loops)
    - [for loop](#for-loop)
        - [Infinte for loop](#infinite-for-loop)
    - [while Loop](#while-loop)
        - [Infinite while Loop](#infinite-while-loop)
    - [do while loop](#do-while-loop)
        - [Infinite do while loop](#infinite-do-while-loop)
    - [for vs while loop](#for-vs-while-loop)
  - [break](#break)
  - [continue](#continue)

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

// Switch More Examples
let dayUserInput = prompt('What day is today ?')
let day = dayUserInput.toLowerCase()

switch (day) {
  case 'monday':
    console.log('Today is Monday')
    break
  case 'tuesday':
    console.log('Today is Tuesday')
    break
  case 'wednesday':
    console.log('Today is Wednesday')
    break
  case 'thursday':
    console.log('Today is Thursday')
    break
  case 'friday':
    console.log('Today is Friday')
    break
  case 'saturday':
    console.log('Today is Saturday')
    break
  case 'sunday':
    console.log('Today is Sunday')
    break
  default:
    console.log('It is not a week day.')
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

# Loops

In programming, loops are used to repeat a block of code.

For example, if you want to show a message 100 times, then you can use a loop. It's just a simple example; you can achieve much more with loops.

## for loop

The syntax of the for loop is:

```js
for (initialExpression; condition; updateExpression) {
    // for loop body
}
```

Here

1. The initialExpression initializes and/or declares variables and executes only once.
2. The condition is evaluated.
    1. If the condition is false, the for loop is terminated.
    2. If the condition is true, the block of code inside of the for loop is executed.
3. The updateExpression updates the value of initialExpression when the condition is true.
4. The condition is evaluated again. This process continues until the condition is false.

**Example**

Display a Text Five Times

```js
// program to display text 5 times
const n = 5;

// looping from i = 1 to 5
for (let i = 1; i <= n; i++) {
    console.log(`I love JavaScript.`);
}
```

**Output**

```
I love JavaScript.
I love JavaScript.
I love JavaScript.
I love JavaScript.
I love JavaScript.
```

### Infinite for loop

If the test condition in a for loop is always true, it runs forever (until memory is full).

```js
// infinite for loop
for(let i = 1; i > 0; i++) {
    // block of code
}
```

## while Loop

The syntax of the while loop is:

```js
while (condition) {
    // body of loop
}
```

Here ,

1. A while loop evaluates the condition inside the parenthesis ().
2. If the condition evaluates to true, the code inside the while loop is executed.
3. The condition is evaluated again.
4. This process continues until the condition is false.
5. When the condition evaluates to false, the loop stops.

**Example**

Display Numbers from 1 to 5

```js
// program to display numbers from 1 to 5
// initialize the variable
let i = 1, n = 5;

// while loop from i = 1 to 5
while (i <= n) {
    console.log(i);
    i += 1;
}
```

**Output**
```
1
2
3
4
5
```

### Infinite while Loop

If the condition of a loop is always true, the loop runs for infinite times (until the memory is full).

```js
// infinite while loop
while(true){
    // body of loop
}
```

## do while loop

The syntax of do...while loop is:

```js
do {
    // body of loop
} while(condition)
```

Here, 
1. The body of the loop is executed at first. Then the condition is evaluated.
2. If the condition evaluates to true, the body of the loop inside the do statement is executed again.
3. The condition is evaluated once again.
4. If the condition evaluates to true, the body of the loop inside the do statement is executed again.
5. This process continues until the condition evaluates to false. Then the loop stops.

**Note:** do-while loop is similar to the while loop. The only difference is that in do…while loop, the body of loop is executed at least once.


### Infinite do while Loop

```js
// infinite do...while loop
const count = 1;
do {
   // body of loop
} while(count == 1)
```

## for Vs while Loop

A for loop is usually used when the number of iterations is known. For example,

```js
// this loop is iterated 5 times
for (let i = 1; i <=5; ++i) {
   // body of loop
}
```
And while and do...while loops are usually used when the number of iterations are unknown. For example,

```js
while (condition) {
    // body of loop
}
```

## break

Break is used to interrupt a loop.

```js
for(let i = 0; i <= 5; i++){
  if(i == 3){
    break
  }
  console.log(i)
}

// 0 1 2
```

The above code stops if 3 found in the iteration process.

## continue

We use the keyword *continue* to skip a certain iterations. 

```js
for(let i = 0; i <= 5; i++){
  if(i == 3){
    continue
  }
  console.log(i)
}

// 0 1 2 4 5
```
