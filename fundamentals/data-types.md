- String Interpolation

  ```jsx
  let greetings = 'Yoo my name is Finesse';
  let secondSentence = 'What is your name?';

  console.log(`${greetings}. I am a student at GA. ${secondSentence}`);
  ```

- Escape Sequences

  ```jsx
  let str = "What's your name?";
  console.log(str);

  console.log('Hey\nyou');
  ```

- Numbers

  ```jsx

  ```

- Modulus

  ```jsx

  ```

- Booleans
  - Will always be true or false
- Logical Operators

  ```jsx
  const pizza = false
  const chipotle = false

  ! -- NOT
  console.log(!pizza)
  console.log(!chipotle)

  && -- AND -checks values on either side
  const happy = pizza && chipotle

  || -- OR -checks for one correct value
  const happy = !pizza || !chipotle
  console.log(happy)
  ```

- Arrays

  ```jsx
  // const mountRushmore = ["Washington", "Jefferson", "Roosevelt"]
  // mountRushmore.push("Lincoln")
  // console.log(mountRushmore)

  // const letters = [
  //   ["a", "b", "c"],
  //   ["d", "e", "f"],
  //   ["g", "h", "i"],
  // ]

  // let mixed = [
  //   { object: "value" },
  //   "one string",
  //   function () {
  //     console.log("I'm fun");
  //   },
  //   0,
  //   "a second string",
  // ]
  ```

- Objects

  ```jsx
  let student = {
    name: 'Kway',
    age: 25,
    profession: 'Software Engineer'
    walk: () => {
      console.log('I am walking')
    }
  }
  ```

- String Methods

  // let greetings = "Hi there friend!"
  // //9 is starting position and 6 is length
  // let buddy = greetings.substr(9, 6)
  // console.log(buddy)

  // let greeting = "Hello"
  // let place = "Las Vegas"
  // //will probably never use because of string interpolation
  // console.log(greeting.concat(" ", place))
  // console.log(`${greeting} ${place}`)

  // let nooo = "Luke, I am your father"
  // console.log(nooo.indexOf("father"))

  // //split a string into an array, determined by the separator you pass in
  // let phrase = 'Rubber baby buggy bumpers is a hard one'
  // const phraseArr = phrase.split(" ")

  // console.log(phraseArr)

  // console.log(phraseArr.length)

  // //converts number to a string (opposite of parseInt)
  // let makeMeAString = 58320
  // console.log(makeMeAString)
  // console.log(makeMeAString.toString())

  // //trims the end of the number after the decimal to the specified argument
  // let makeMeFixed = 187.73242
  // let fixed = makeMeFixed.toFixed(2)
  // console.log(fixed)
