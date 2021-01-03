# What is JavaScript?

- JavaScript is a dynamic language used to make the page, and objects on the page, behave a certain way
- it is a case sensitive language that helps in making interactive web pages and is interpreted and executed on the client machine
- it is used as default scripting language for HTML and reduces the load on the server as some operation is done on client side
- it is an OOP scripting language that only runs on a browser and code is interpreted /Just In Time (JIT) compiled before execution
- JavaScript code must be inserted after the <body> tab for page to fully render properly
    - there is no limit to number of .js files that can be linked to a .html file

    ```html
    <script src="filename.js"></script>
    ```

- JavaScript uses camelCasing (lowercase first word and uppercase first letter of following words)
- Data Types
    - Number === numeric value (no technical difference between integers and floats)
    - Boolean === True or False
    - String === characters in single/double quotes
    - Null === it as one specific value ***null***
    - Arrays === indexable list of items
    - Object === group of attributable value pairs
    - Special Values
        - NaN === not a number
        - Undefined === a declared variable is not defined
    - Variables
        - javascript variables can be considered as containers, which store a particular value or name for a particular block of memory
        - will usually be denoted as var = *variableName*
        - javascript variables has standardized naming conventions:
            - do not use JavaScript Keywords such as ***if, for, do*** and ***function***
            - do not start with a digit
            - do not use special characters (%, $, &) inside the name
            - start with an alphabet or followed by an alphabet or digits or underscore
            - can use uppercase or lowercase alphabets
    - Arrays
        - denoted using [..] square brackets

        ```jsx
        // Declaration Examples

        var space = ['moon', 'star', 'sun'];
        					OR
        var space = newArray('moon', 'star', 'sun');

        //Accessing Elements Examples

        var bodies = space[0] + space[1] + space[3];
        /* bodies will have the value 'moon star sun' */
        					OR
        space[0] = 'planet';
        /* the first element of the space array will have the value 'planet' */
        ```

        - 
    - Type Conversions
        - Type Conversions/ Type Casting: a process where an entity of one data type is converted to another
        - there are two ways in which Type Conversion is done in JavaScript
            - implicit conversion: integers converted to Strings and back automatically
            - explicit conversion: use JavaScript functions like parseInt( ), parseFloat( ), etc
- Operators
    - Some of the operators use in JavaScript are:
        - Arithmetic
            - +addition
            - -subrtraction
            - *multiplication
            - /division
            - %modulus
            - ++increment
            - - -decrement
            - - unary minus
        - String
            - +concatenation
        - Assignment
            - =assignment
            - +=add, assign
            - -=subtract, assign
            - *=multiply, assign
            - /=divide, assign
            - %= mod, assign
        - Comparison
            - ==equal
            - ! =not equal
            - >greater
            - <lesser
            - .> =greater/equal
            - .< =lesser/equal
            - ===equal value and same type
            - ! ==not equal value or same type
        - Boolean
            - &&AND
            - ||OR
            - !NOT
        - Ternary
            - shortens if else statements

            The ternary operator is a substitute for an *if* statement in which both the *if* and *else* clauses assign different values to the same field, like so:

            ```jsx
            if (condition)result = 'something';elseresult = 'somethingelse';
            ```

            The ternary operator shortens this if/else statement into a single statement:

            ```jsx
            result = (condition) ? 'something' : 'somethingelse';
            ```

            If *condition* is true, the ternary operator returns the value of the first expression; otherwise, it returns the value of the second expression.

            - variable_name=(condition)?value1:value2;
            - /* if the condition is true variable_name will be assigned value1, or else value2 */
- Conditional Statements
    - if
        - condition expression evaluates to a Boolean value
        - if the condition expression evaluates to true the block is executed
        - if the condition expression evaluates to false, then the block is skipped
    - if-else
        - if the condition expression evaluates to true, then the block following the condition is executed
        - if condition expression evaluates to false, then the block following the else keyboard is executed
    - if-else-if-else
        - if-else statements can be cascaded
        - two if conditions are checked, and returns a Boolean value
        - if both the if conditions return false, then this else block statement is executed
    - switch
        - test Expression
            - evaluated to an integer, floating-point number, string, or Boolean value
        - case Statements
            - contains the different values a test expression evaluates to
            - permitted case values
                - integer, floating-point number, string, or Boolean values
            - a group of statements are executed (followed by break statement)
        - break Statement
            - breaks the execution of group of statements following case
        - default Statement
            - matched when test expression does not match the listed case statements

            Use the `switch` statement to select one of many code blocks to be executed.

            ```jsx
            switch(expression) {
              case x:
                // code block
                break;
              case y:
                // code block
                break;
              default:
                // code block
            }
            ```

            This is how it works:

            - The switch expression is evaluated once.
            - The value of the expression is compared with the values of each case.
            - If there is a match, the associated block of code is executed.
            - If there is no match, the default code block is executed.
- Loops
    - loops are basically blocks of code that are to be executed for a number of times
    - JavaScript supports different kinds of loops:
        - `for` - loops through a block of code a number of times
        - `for/in` - loops through the properties of an object
        - `for/of` - loops through the values of an iterable object
        - `while` - loops through a block of code while a specified condition is true
        - `do/while` - also loops through a block of code while a specified condition is true
    - the loop will keep on executing until the condition check returns false
    - The FOR loop has the following syntax:

        ```jsx
        for (statement 1; statement 2; statement 3) {
          // code block to be executed
        }
        ///////
        for (i = 0; i < 5; i++) {
          text += "The number is " + i + "<br>";
        }
        ```

        **Statement 1** is executed (one time) before the execution of the code block.

        **Statement 2** defines the condition for executing the code block.

        **Statement 3** is executed (every time) after the code block has been executed.

        From the example above, you can read:

        Statement 1 sets a variable before the loop starts (var i = 0).

        Statement 2 defines the condition for the loop to run (i must be less than 5).

        Statement 3 increases a value (i++) each time the code block in the loop has been executed.

    - the WHILE LOOP loops through a block of code as long as a specified condition is true

    ```jsx
    while (condition) {
      // code block to be executed
    }
    ///////
    while (i < 10) {
      text += "The number is " + i;
      i++;
    }
    ```

- Functions
    - A JavaScript function is a block of code designed to perform a particular task.
    - A JavaScript function is executed when "something" invokes it (calls it)

    ```jsx
    function myFunction(p1, p2) {
      return p1 * p2;   // The function returns the product of p1 and p2
    }
    ```

    - A JavaScript function is defined with the `function` keyword, followed by a **name**, followed by parentheses **( )**.
    - Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).
    - The parentheses may include parameter names separated by commas:**(*parameter1, parameter2, ...*)**
    - The code to be executed, by the function, is placed inside curly brackets: **{}**

    ```jsx
    function name(parameter1, parameter2, parameter3) {
      // code to be executed
    }
    ```

    - Function **parameters** are listed inside the parentheses ( ) in the function definition.
    - Function **arguments** are the **values** received by the function when it is invoked.
    - Inside the function, the arguments (the parameters) behave as local variables.
    - Functions can be categorized in 4 types
        - Named
            - has a unique name
            - can be called/used multiple places
        - Anonymous
            - does not have a name
            - can be used at one place only (when it is called immediately after it is defined, or actual argument to function)
            - the function defined is used as an expression
            - can be stored in a variable
            - passed as an actual argument to a function
            - can be returned as a value by a function
        - Self Invoking
            - anonymous and are invoked right after the function has been defined
            - you can execute the code once, without declaring any global variables
            - no reference is maintained to this function, not even to its return value
        - Constructors
            - called when an object is created using the new keyword
- Closures
    - it is an implicit permanent link between the function and its scope chain
    - a function definition's (Lamda) hidden [[scope]] ("[[ ]]") denotes internal property) reference:
        - holds the Scope Chain (preventing Garbage Collection)
        - it is used and copied as the "outer environment reference" anytime the function is run
    - a closure is created whenever a function is created and is used to ensure the information in the function
        - A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. Among other things, closures are commonly used to give objects data privacy.
- Object
    - Object are variables that can hold many values
    - object creation:
        - with a new keyword

            ```jsx
            var person = new Object( );
            person.name = "John";
            person.age = 46;
            ```

        - or can be created with initial set of properties (attributes) with .(dot)

            ```jsx
            var person = {};
            person.name = "John";
            person.age = 46;
            ```

    - objects have two distinct traits
        - properties: what it possesses
        - and methods/functionality: what it can do
    - object property creation:
        - creating initial set of properties (attributes) with [ ]

            ```jsx
            var person = {};
            person['name'] = "John";
            person['age'] = 46;
            ```

        - creating with initial set of properties (attributes) with { }

            ```jsx
            var person = {name: "saya", age: 46};
            alert("Your name is: " + person.name + "\nYour age is: " + person.age);
            ```

    - to delete an object property

        ```jsx
        delete person.age;
        ```

- Browser Object Model (BOM)
    - Browser Objects are global objects
    - available through the JavaScript code
    - BOM allows JavaScript code to interact with the browser properties
    - Window Object
        - represents the browser's window
        - global variables are properties of the window object
        - global functions are methods of the window object
        - even the document object 9of the HTML DOM) is a property of the window object
            - window.open() - open a new window
            - window.close() - close the current window
            - window.moveTo() - move the current window
            - window.resizeTo() - resize the current window
        - examples of Window Object can be see further in examples below as they are all window objects:
            - location object
                - refers to website address and can be used to get the current page address (URL) and redirect the browser to a new page (among other things)
            - history object
                - contains the browser's history
                - examples like ***history.back()*** will go back a page and ***history.forward()*** will go forward a page etc.
            - screen object
                - contains information of the user's screen
                - window.screen object can be written without the Window prefix
            - navigator object
                - contains information of the visitor's browser
                - window.navigator object can be written without the window prefix
            - document object
                - forms object
                - images object
                - links object
- Document Object Model
    - the HTML DOM is a standard object model and programming interface for HTML
    - it defines:
        - the HTML elements as objects
        - the properties of all HTML elements
        - the methods to access all HTML elemets
        - the events for all HTML elements
    - Document Object Model of the page is created by the browser, when a webpage is loaded
    - the HTML DOM model is constructed as a tree of Objects
    - What can JavaScript do with DOM?
        - JavaScript + DOM = dynamic HTML on Client-Side
        - change all the HTML elements and attributes in the page
        - change all the CSS styles in the page
        - add and remove existing HTML elements and attributes
        - JavaScript can react to all existing HTMNL events in the page
        - JavaScript can create new HTML events in the page
    - the document object represents your webpage and to access any HTML element, you will start with accessing the document object and DOM methods to find them

    ```jsx
    //gets the HTML Element with specified ID
    getElementById()Method

    //gets the HTML Element with specified specified class name
    getElementByClassName()Method

    //gets the HTML Element with specified element tag
    getElementByTagName()Method
    ```

---

- Extra Stuff
    - inline comments have // and won't be read by the program; multi line comments have /*  ....  */  to separate things out
    - a parameter (*name*) is what we have at the time of declaration and an argument (*John*) is the actual value that is supplied to that parameter

    ```jsx
    function greet(name) {
    	console.log('Hello' + name);
    }
    greet('John')
    ```

    - indexing begins with 0 like in most other computer stuff