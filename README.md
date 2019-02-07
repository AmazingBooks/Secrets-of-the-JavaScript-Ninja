# Secrets of the JavaScript Ninja
Is a solid book resource for the current state of using JavaScript.

## Short ES6 reminder:
- **Template literals** - are embed expressions into strings: `${ninja}`. 
- **Block-scoped variables:**
```javascript
- Use the new let keyword to create block-level variables: let ninja = "Yoshi".
- Use the new const keyword to create block-level constant variables whose value 
      can’t be reassigned to a completely new value: const ninja = "Yoshi".
  
```
- **Function parameters:**

```javascript
- Rest parameters create an array from arguments that weren’t matched to parameters: 
  let first = 3,  remaining =  [3, 4, 5]; 
  
  function multiMax(first, ...remaining){ /*...*/}
           multiMax(2, 3, 4, 5); 
           //first: 2;
           // remaining: [3, 4, 5]
           
- Default parameters specify default parameter values that are used if no value is supplied during invocation: 
    
    function do(ninja, action = "skulk" ){ 
          
            return ninja + " " + action;

        }
         
         do("Fuma"); //"Fuma skulk"

```
- **Spread operators** expand an expression where multiple items are needed: [...items, 3, 4, 5].
- **Arrow functions** let us create functions with less **syntactic clutter**. 
```javascript

They don’t have their own this parameter. Instead, they inherit it from the context in which they were created: 

      const values = [0, 3, 2, 5, 7, 4, 8, 1];
      
      values.sort((v1,v2) => v1  - v2); /*OR*/ 
      values.sort((v1,v2) => { return v1  - v2;});
      value.forEach(value => console.log(value));

```

- **Generators** -  generate sequences of values on a per-request basis. Once a value is generated, the generator suspends its execution without blocking. Use __yield__ to generate values: 

```javascript

      function *IdGenerator(){
        let id = 0;
        while(true){ yield ++id; }
      }
      
```




```javascript

      function *IdGenerator(){
        let id = 0;
        while(true){ yield ++id; }
      }
      
```

- __Promises__ - are placeholders for the result of a computation. A promise is a guarantee that eventually we’ll know the result of some computation. The promise can either succeed or fail, and once it has done so, there will be no more changes: 

```Javascrip

- Create a new promise with: 
      new Promise((resolve, reject) => {});. 
      
- Call the resolve function to explicitly resolve a promise. Call the reject function to explicitly reject a promise. A promise is implicitly rejected if an error occurs. 

- The promise object has a then method that returns a promise and takes in two callbacks, a success callback and a failure callback: 

           myPromise.then(val => console.log("Success"), err => console.log("Error"));
           
Chain in a catch method to catch promise failures: myPromise.catch(e => alert(e));. 

```
- __Classes__ - act as syntactic sugar around JavaScript’s prototypes: 


```Javascript

      class Person {
        constructor(name){ this.name = name; }
        dance(){ return true; }
      }
      
      class Ninja extends Person {
        
        constructor(name, level){
          super(name);
          this.level = level;
        }
        
        static compare(ninja1, ninja2){
          return ninja1.level - ninja2.level;
        }
        
      }
```

- __Proxies__ - control access to other objects. Custom actions can be executed when an object is interacted with (for example, when a property is read or a function is called): 


```Javascript

      const p = new Proxy(target, {
        get: (target, key) => { /*Called when property accessed through proxy*/ },
        set: (target, key, value) => { /*Called when property set through proxy*/ }
      });

```

- __Maps__ - are mappings between a key and a value: 

```C++

- new Map() creates a new map. 
- Use the set method to add a new mapping, the get method to fetch a mapping, the has method to check whether 
      a mapping exists, and the  delete method to remove a mapping. 

```
- __Sets__ - are collections of unique items: 

```C++

- new Set() creates a new set. 
- Use the add method to add a new item, the delete method to remove an item, 
      and the size property to check the number of items in a set. 

```
- __for...of loops__ - iterate over collections and generators. 
- __Destructuring__ - extracts data from objects and arrays: 

```C++

- const {name: ninjaName} = ninja;
- const [firstNinja] = ["Yoshi"];

```

- __Modules__ are larger units of organizing code that allow us to divide programs into clusters: 

```C++

      export class Ninja{}; //Export an item
      export default class Ninja{} //Default export
      export {ninja};//Export existing variables
      export {ninja as samurai}; //Rename an export

      import Ninja from "Ninja.js"; //Import a default export
      import {ninja} from "Ninja.js"; //Import named exports
      import * as Ninja from "Ninja.js"; //Import all named exports
      import {ninja as iNinja} from "Ninja.js"; //Import with a new name

```





# Table of Contents
1. [Chapter 1. JavaScript is everywhere ](#Chapter 1. JavaScript is everywhere )
2. [Example2](#example2)
3. [Third Example](#third-example)

## Chapter 1. JavaScript is everywhere 
## Example2
## Third Example











