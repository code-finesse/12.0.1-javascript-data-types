# Javascript Control Flow and Loops

- Conditionals

    ```jsx
    let age = 16

    if(age >=16){
      console.log ('You can drive!')
    }

    console.log('Hey what\'s up')

    for (let i = 0; i < 5; i++) {
      console.log("hello world");
    }

    let temp = 75;

    while (temp >= 70) {
      console.log("Wow it is really HOT!");
      // temp = temp -=1
      temp -= 1;
    }

    console.log("Ah that's better");
    ```

    - Truthinesse & Falsiness
    - Truthy values: any string/number with a value -- anything not an empty string and any number other than 0
    - Falsey values: 0, '' -- empty string, undefined, null
        - undefined means it exists with no value and not defined means it doesn't exist

    ```jsx
    let dog = true
    if (dog) {
      console.log('Woof woof')
    }

    let cat = 'feline'
    if (cat) {
        console.log('Meowwwww')
    } else {
        console.log('no meow')
    }
    ```

    ```jsx
    let California = 'sunny'
    if (true && 8 < 24 && California) {
        console.log('Kobe!')
    }

    if (true || false) {
      console.log('I think I\'m gettin the hang of this')
    }
    ```

- Loops
    - First argument in for loop (iterator): starting point that initilaizes a variable and set it to where you want yourl oop to start
    - Second argument in a for loop (condition): while this condition is true the loop will execute the ode inside the curly brackets
    - Last argument in a for loop (incrementer): what to do with the iterator after executing the block of code inside the curly brackets

    ```jsx
    for (let i = 0; i < 5; i++) {
      console.log(`Logging i ${i}`)

    }

    for (let i = 0; i < 100; i += 5) {
      console.log(i);
    }

    for (let i = 100; i >= 0; i--) {
      console.log(i)
    }
    ```

    Iterating Over Arrays

    ```jsx
    let sports = ['basketball', 'football', 'soccer', 'baseball', 'hockey']
    let leagues = ['NBA', 'NFL', 'MLS', 'MLB', 'NHL']
    // console.log(sports.length)

    for (let i = 0; i < sports.length; i++) {
      console.log(`They play ${sports[i]} in ${leagues[i]}`)
    }

    let num = 0
    while (num <= 10) {
        console.log(num)
        num += 1
    }
    ```
