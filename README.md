# Secrets of the JavaScript Ninja

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
