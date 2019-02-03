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
