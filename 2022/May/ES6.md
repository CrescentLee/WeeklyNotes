## ES6 Notes

###### May-2022

1. General Features

   * const, unchangable once declared, but the element inside the object can be changed

```javascript
const A = [1,2,3];
s = [2,3,4]; //report error
s[2] = 4; //become [1,2,4];
```

	To prevent object mutation, use `Object.freeze` to proceed.

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

    * Rest Parameter `...`, this is an important feature in ES6. Ususally when we use rest parameter, the input is array.

```javascript
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}
console.log(howMany(0, 1, 2)); //You have passed 3 arguments.
console.log(howMany("string", null, [1, 2, 3], { })); //You have passed 4 arguments.

```
