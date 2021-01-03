# Javascript Testing

Mocha is a framework but we're using it as a test runner

Chai is an assertion library to make sure that our tests result in our expected outcome

Supertest tests HTTP requests to make sure that routes and endpoints work

1. install mocha, chai, and supertest node modules

    ```jsx
    // in terminal
    $ npm install mocha chai supertest
    ```

2. open a separate terminal tab and run nodemon
3. create a test folder and put candies.test.js file inside it

    ```jsx
    // in terminal
    mkdir test
    $ touch test/candies.test.js
    ```

4. just for curiosity

    ```jsx
    GET /candies 200 4.902 ms - 185
    ```

5. create test variables

    inside candies.test.js

    ```jsx
    const should = require('chai').should()
    const expect = require('chai').expect
    const supertest = require('supertest')

    // Pass supertest the API endpoint that we will be using
    const api = supertest('http://localhost:3000')
    ```

6. create describe function

    inside candies.test.js file

    ```jsx
    describe("GET /candies", () => {
      //tests will be written inside this function
    })
    ```

7. set up describe function (for get routes specifically)

    ```jsx
    describe('GET /candies', () => {
      // it takes two arguments
      // first argument tells us what its supposed to do
      // second argument that runs the code and a function you must call when the test is finished (e.g. done)
      it('should return a 200 response', (done) => {
        // supertest which we've assigned to the variable api
        api
          // endpoint
          .get('/candies')
          // sets an http header on the request and specifying what type of data we want to receive (our application will accept json format)
          .set('Accept', 'application/json')
          // tests the response (specifically looking for 200 status code) and tells the it() function we are done
          .expect(200, done)
      })
    })
    ```

    - test blocks

        Every block of code that starts with `it()` represents a test. Each test is performed in sequence, one after the other, in a queue.

        The `callback` represents a function that Mocha will pass to the code so that the next test will be executed only when the current is finished and the `done` function is called - this allows tests to be executed once at a time. It's almost like the resolve function of a `Promise`.

8. run mocha

    ```jsx
    node_modules/.bin/mocha
    ```

9. change script in package.json so we can run test easier

    now we can just run npm test

    ```jsx
    {
      ...
      "scripts": {
        "test": "node_modules/.bin/mocha"
      },
      ...
    }
    ```

10. set up test to check for an array

    ```jsx
    // previous it function
    })
    // still inside describe
      it('should be an array', (done) => {
        api
          .get('/candies')
          .set('Accept', 'application/json')
          .end((err, res) => {
            expect(res.body).to.be.an('array')
            done()
          })
      })
    })
    ```

11. set up a test to check if the field (in this example it is json data set in an array) has a specific property

    ```jsx
    it('should return an array of objects that have a field called "name" ', (done) => {
        api
          .get('/candies')
          .set('Accept', 'application/json')
          .end((err, res) => {
            // res.body is an array so we can loop through it (why we're using for each)
            res.body.forEach((candy) => {
              // each candy should have a property called name
              expect(candy).to.have.property('name')
            })
    				// we want the done to happen outside of the for loop (it will only return after the first iteration, like having a return at the end of a for loop)
            done()
          })
      })
    ```

12. create describe function (for post routes specifically) for testing sending data to the server

    ```jsx
    describe('POST /candies', () => {
      
    })
    ```

13. create an object to be sent

    ```jsx
    // inside describe function
    // creating a new object to test
      const newCandy = {
        id: 5,
        name: 'Now & later',
        color: "purple"
      }
    ```

14. create a before block to send the data to the api

    ```jsx
    // still inside describe function
    // before will run once before all the tests in the describe block
      before((done) => {
        // call to the api
        api
          .post('/candies')
          .set('Accept', 'application/json')
          // attempt to send new object
          .send(newCandy)
          .end(done)
      })
    ```

15. create the test to check if it was posted
    - example 1

        ```jsx
        // still inside describe function
        // actual test to run after the before block
          it('should add a candy object to the collection candies and return it', (done) => {
            api
              .get('/candies')
              .set('Accept', 'aplication/json')
              // end with a callback function inside of it
              .end((err, res) => {
                // create a new variable (candy) 
                // find something in the body with the same id of our newCandy
                let candy = res.body.find((cando) => cando.id === newCandy.id)
                // once we find it we expect it to be an object
                expect(candy).to.be.an('object')
                done()
              })
          })
        ```

    - example 2

        ```jsx
        // still inside describe function
        it('should add a candy object to the collection candies and return it', done => {
            api
              .get('/candies')
              .set('Accept', 'application/json')
              .end((error, response) => {
                expect(response.body.find(candy => candy.id === newCandy.id)).to.be.an(
                  'object'
                );
                done();
              });
          });
        ```

- Full GET Test

    ```jsx
    describe('GET /candies', () => {
      it('should return a 200 response', (done) => {
        api
          .get('/candies')
          .set('Accept', 'application/json')
          .expect(200, done)
      })

      it('should be an array', (done) => {
        api
          .get('/candies')
          .set('Accept', 'application/json')
          .end((err, res) => {
            expect(res.body).to.be.an('array')
            done()
          })
      })

      it('should return an array of objects that have a field called "name" ', (done) => {
        api
          .get('/candies')
          .set('Accept', 'application/json')
          .end((err, res) => {
            res.body.forEach((candy) => {
              expect(candy).to.have.property('name')
            })
            done()
          })
      })
    })
    ```

- Full POST Test

    ```jsx
    describe('POST /candies', () => {
      const newCandy = {
        id: 5,
        name: 'Now & later',
        color: "purple"
      }

      before((done) => {
        api
          .post('/candies')
          .set('Accept', 'application/json')
          .send(newCandy)
          .end(done)
      })

      it('should add a candy object to the collection candies and return it', (done) => {
    		api
          .get('/candies')
          .set('Accept', 'application/json')
          .end((error, response) => {
            expect(response.body.find(candy => candy.id === newCandy.id)).to.be.an(
              'object'
            );
            done();
          });
    })
    ```
