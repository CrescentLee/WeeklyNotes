## ES6 Notes

###### May-2022

1. General Features

  * const, unchangable once declared, but the element inside the object can be changed

  ```javascript
  const A = [1,2,3];
  s = [2,3,4]; //report error
  s[2] = 4; //become [1,2,4];
  ```
  * To prevent object mutation, use `Object.freeze` to proceed.

  ```javascript
  let obj = {name: "ABC"};
  Object.freeze(obj);
  ```

  * Arrow function

  ```javascript
  const myFunction = () => {return true;}
  const myFunWithVar = (var1, var2) => {return var1 + var2;}
  const myFunction2 = (name = "ABC") => "Hello " + name;
  myFunction2(); // write Hello ABC
  myFunction2('CDE'); // write Hello CDE
  ```

  * Rest/Spread Parameter `...`, this is an important feature in ES6. Ususally when we use rest parameter, the input is array.

  ```javascript
  function howMany(...args) {
    eturn "You have passed " + args.length + " arguments.";
  }
  console.log(howMany(0, 1, 2)); //You have passed 3 arguments.
  console.log(howMany("string", null, [1, 2, 3], { })); //You have passed 4 arguments.
  ```
2. ES6 Syntax
  * Desctructuring assignment
  ```javascript
  const user = { name: 'ABC' , age: 34 }
  const { name, age} = user
  const [a, b,,, c] = [1,2,3,4,5,6];
  //a = 1, b = 2, c = 5
  const [a, b, ...arr] = [1,2,3,4,5,6,7];
  //a = 1, b = 2, arr = [3,4,5,6,7];
  ```
  * Tempalte literal
  ```javascript
  const person = {
    name: "Zodiac Hasbro",
    age: 56
  };

  const greeting = `Hello, my name is ${person.name}!
  I am ${person.age} years old.`;
  ```
  * Concise declarative function
  ```javascript
  const person = {
    name:"Taylor",
    sayHello: function(){
      return 'Hello, name is ${this.name}';
    }
  }
  ```
  * Class
  ```javascript
  class Vegetable(){
    constructor(name){
      this.name = name;
    }
  }
  const carrot = new Vegetable('carrot');
  ```
  * getter and setter, used to set/get the value of a property within an object, which can set/get values without touching the internal code.
  ```javascript
  class Book {
    constructor(author){
      this._author = author;
    }
    get writer(){
      return this._author;
    }
    set writer(new_author){
      this._author = new_author;
    }
  }
  const novel = new Book('anonymous'); //_author set to anonymous
  console.log(novel.writer);
  novel.writer = 'ABC' //_author set to ABC
  console.log(novel.writer);
  ```
3. Module
  * Module script
  ```HTML
  <script tyle="module" src="file.js"></script>
  ```
  * Export and import
  ```javascript
  //export
  const add = (x,y) =>{return x + y;}
  export {add,subtract ....}
  //import
  import {add} from './math_functions.js';
  import * as myMythModule from './math_functions.js';
  //export default
  export default function add(x, y) {
    return x + y;
  }
  //import a default export
  import add from "./math_functions.js";
  ```
4. Promise
  The most significant feature introduced in ES6. You use it to make a promise to do something, usually asynchronously. Whne the task completes, you either fulfill your promise or failed to do so. Resolve or reject.
  ```javascript
  const myPromise = new Promise((resolve,reject) =>{

  });
  ```
  A promise has 3 states: pending, fulfilled and rejected. user resolve() and reject() for states update.
  ```javascript
  const myPromise = new Promise((resolve,reject) =>{
    if(condition){
      resolve("Promise was fulfilled");
    } else{
      reject("Promise was rejected");
    }
  })
  ```
  `then` is a keyword used in promise, the `then` method is executed immediately after the promise is fufilled with resolve.
  ```javascript
  myPromise.then(result =>{

  });
  ```
  `catch` is a keyword used in promise, the `catch` method is executed immediately after the promise is rejected with reject.
  ```javascript
  myPromise.catch(error =>{

  });
  ```
5. Spread Operator in array
  ```javascript
  let thisArray = ['A',2,3,4,5,'C'];
  let thatArray = [...thisArray]
  let thirdArray = [1,2,...thisArray,'D'] //[1,2,'A',2,3,4,5,'C','D']
  ```

