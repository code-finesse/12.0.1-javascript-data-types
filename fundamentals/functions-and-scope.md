# Javascript Functions and Scope

## Function Basics

- javascript is in ES6 ECMAscript specifications
    - ECMAscript = European Computer Manufactures Association
- once you know code works delete all console.log s
- all functions return as undefined unless we tell it otherwise

1. Start every function with the structure
2. Give it a descriptive name
3. Add any parameters as variables to use **inside** the function
4. Split the curly braces and write your code inside the code block
5. Invoke the function

```jsx

function addTwoNumbers(num1, num2) {
//   // the return keyword provides output for our function
//	// AND causes the function to be exited
	return num1 + num2
//   // nothing following a return will ever be executed
	console.log('num1 is ', num1);
	console.log('num2 is ', num2);
	console.log(num1 + num2)
}
```

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d7b2b83f-7600-45d9-8e85-f5c0de3b295f/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d7b2b83f-7600-45d9-8e85-f5c0de3b295f/Untitled.png)

```jsx
// Changing a variable outside of the function is a side-effect
// Any tme you are changing a variable outside of your function you are
// potentially inctroducing bugs into your code

// Output uses return and stores a keyword inside the variable
// Side effect sets a variable outside of the function that it 
//changes inside othe function
```

# Function Expression

How the JS Engine reads our code

1. Parses and tokenizes our code into a tree

2. When it encounters a function keyword, it stores the corresponding function in memory

3. When it encounters a variable, it creates a place in memory for the variable

```jsx
// FUNCTION DECLARATION SYNTAX
function multiply (num1, num2) {
	return num1 * num2
}

console.log(multiply(5, 8))
```

// FUNCTION EXPRESSION SYNTAX

- Causes an Uncaught TypeError because is hoisted but the assignment is NOT so the compputer sees var multiply

```jsx
multiply(3, 5)
// the multiply variable is a given value:
var multiply = function (num1, num2) {
  return num1 * num2
}
```

# Hoisting

RULES FOR HOISTING

1. variables defined without a keyword are hoisted

2. variable defined with the var keyword are hoisted

- Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function)
- to avoid bugs, always declare all variables at the beginning of every scope

//////////// THIS MAKES THE MOST SENSE AS AN EXPLANATION /////////////////

- How does a function declaration differ from a function expression?
    - A function expression follows the same rules as variable assignment. Since the value of the reference is a function, that function is only available after the assignment.
    - With a function declaration, no matter where you put it in your code, it behaves as if you wrote it as the very first line in your code.
    - Aside from that, they are functionally equivalent.

# Arrow Functions

Normally looks like this

```jsx
const square = function(num1) {
  return num1 * num1
}
```

We can turn this into an arrow function by following the steps below:

1. Drop the function keyword
2. Add a fat arrow after the parameters

```jsx
const squre = (num1) => {
  return num1 * num1
}

// 3. OPTIONALLY, if there is only one line with a return, then delete the curly braces and the return keyword
// const square = (num1) => num1 * num1;

// 4. OPTIONALLY, if there is only one parameter, drop the parenthesis on the parameter
const square = num1 => num1 * num1;

// ** Will help with array iteration functions
```

*** Arrow functions are not hoisted

# Scope

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9ff5023b-98c7-4377-b076-4f9311d6d197/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9ff5023b-98c7-4377-b076-4f9311d6d197/Untitled.png)
