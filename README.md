# Secrets of the JavaScript Ninja
Is a solid book resource for the current state of using JavaScript.


# Table of Contents
1. [JavaScript is everywhere](#JavaScript-is-everywhere )
2. [TBC](#TBC)


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

## JavaScript is everywhere 
### The core language features of JavaScript 
__Functions are first-class objects__— In JavaScript, functions coexist with, and can be treated like, any other JavaScript object. They can be created through literals, referenced by variables, passed around as function arguments, and even returned as function return values. We devote much of chapter 3 to exploring some of the wonderful benefits that functions as first-class objects bring to our JavaScript code. 

__Function closures__— The concept of function closures is generally poorly understood, but at the same time it fundamentally and irrevocably exemplifies the importance of functions to JavaScript. For now, it’s enough to know that a function is a closure when it actively maintains (“closes over”) the external variables used in its body. 

__SCOPES__— Until recently(ES6), JavaScript didn’t have block-level variables; instead, we had to rely only on global variables and function-level variables. 

__Prototype-based object orientation__— Unlike other mainstream programming languages, which use class-based object orientation, JavaScript uses prototypes. 

JavaScript consists of a close relationship between __objects__, __prototypes__, __functions and __closures__. Thus understanding the strong relationships between these concepts can vastly improve your JavaScript programming ability, giving you a strong foundation for any type of __Application Development__, regardless of whether your JavaScript code will be executed in a web page, in a desktop app, in a mobile app, or on the server. 

#### How will JavaScript evolve? 
The ECMAScript committee, in charge of standardizing the language, has just finished the ES8/ES2017 version of JavaScript. The ES8 version is a relatively small upgrade to JavaScript (at least, when compared to ES6), because the committee’s goal going forward is to focus on smaller, yearly incremental changes to the language. Yearly incremental updates to the language specification are excellent news, but this doesn’t mean that web developers will instantly have access to the new features after the specification has been released. JavaScript code has to be executed by a Java-Script engine. Unfortunately, although the JavaScript engine developers are trying to keep up and are doing better all the time, there’s always a chance to run into features that are yet to be supported. 

#### What are Transpilers(“transformation + compiling”)?
- Tools that take cutting-edge JavaScript code and transform it into similar code, which works properly in most current browsers.
- Transpilers give us access to tomorrow’s JavaScript today. 

Because of the rapid release cycles of browsers, we usually don’t have to wait long for a JavaScript feature to be supported.But what happens if we want to take advantage of all the benefits of the newest JavaScript features but are taken hostage by a harsh reality: The users of our web applications may still be using older browsers. One answer to this problem is transpilers.

Today’s most popular transpilers are [Traceur](https://github.com/google/traceur-compiler) and [Babel](https://babeljs.io/).
Setting them up by following one of the tutorials: [TRACEUR](https://github.com/google/traceur-compiler/wiki/Getting-Started
) or [BABEL](https://babeljs.io/en/setup/).

#### Understanding the BROWSER 
These days, JavaScript applications can be executed in many environments. But the environment from which it all began, the environment from which all other environments have taken ideas, is the browser.
The main compoents of Browser Infrastructure are:  __CSS, JS, HTML + BROWSER API(DOM, Events and Timers)___.


## TBC












