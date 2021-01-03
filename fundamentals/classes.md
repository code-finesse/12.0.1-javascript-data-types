# Objects and OOP

- watch out for micro-optimizations (just focus on writing good code)
- CRUD (create, read, update, delete)
- For in Loops will be important at the next level
- Object Oriented Programming
    - Encapsulation
        - reduce complexity in implementation (happens when we execute)
    - Abstraction
        - how we design our code (happens when we plan)
    - Inheritance
        - solves the problem on creating things twice (helps keep our code DRYer)
        - gives functionality to a "general user" and gives same functionality  plus some to an "admin"
    - Polymorphism
        - the format of the certain functionalities may be slightly different
        - dogs walk, birds fly, fish swim, but they all move
- JavaScript has  prototypes not classes (but we use them the same way)
- delete keyword can erase keys/values from objects
- Classes

    ```jsx
    class Car {
      constructor(body, make, model) {
        this.body = body;
        this.make = make;
        this.model = model;
        this.available = true;
        this.mileage = 0;
      }
      bookReservation() {
        return (this.available = false);
      }
      returnVehicle() {
        return (this.available = true);
      }
      drive(milesDriven) {
        return (this.mileage += milesDriven);
      }
    }

    const jetta = new Car("sedan", "Volkswagen", "Jetta");

    class User {
      constructor(name, username) {
        this.name = name;
        this.username = username;
      }
      login() {
        "you are logged in";
      }
    }

    ///// INHERITANCE /////

    class Admin extends User {
      constructor(name, username) {
        super(name, username);
        this.isAdmin = true;
      }
    }

    /// extends makes the magic happen ///
    const admin = new Admin("Chris", "Finesse");
    const user = new User("Broke", "Boi");
    ```