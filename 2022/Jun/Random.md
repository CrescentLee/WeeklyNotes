## Regex

#### Jun-2022

Normally random notes
1. Arguement\
   Arguments is a special arrary that is used to proceed multiple input parameter to a function. It does not contain same methods as Array except length. It is built in the function and can proceed any input arguments.
   ```javascript
   //add all number input
   function add(){
      let sum = 0;
      for (var i = 0;i < arugments.length; i++){
         sum+=arguments[i];
      }
      return sum;
   }
   //make an array from arguments
   let args = [...arguments];
   ```
2. Some JS Functions\
   parse functions
   ```javascript
   //parseInt() parse a string argument and returns an integar of the specified radix
   parseInt('01000001', 2)
   parseInt('0xF', 2)
   // return NaN if the conversion is failed, it will check from the first to the end, if have number then convert, if the first element is not number then return NaN.
   //similar for parseFloat()
   parseFloat('3.14');
   ```
   convert to char
   ```javascript
   String.fromCharCode(101)
   ```
