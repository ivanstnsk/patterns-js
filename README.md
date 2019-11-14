# patterns-js
Programming Patterns in JavaScript

### Module
##### Description
Modules are an integral piece of any robust application's architecture and typically help in keeping the units of code for a project both cleanly separated and organized.

The Module pattern was originally defined as a way to provide both private and public encapsulation for classes in conventional software engineering.

In JavaScript, the Module pattern is used to further emulate the concept of classes in such a way that we're able to include both public/private methods and variables inside a single object, thus shielding particular parts from the global scope. What this results in is a reduction in the likelihood of our function names conflicting with other functions defined in additional scripts on the page.

##### History
From a historical perspective, the Module pattern was originally developed by a number of people including Richard Cornford in 2003. It was later popularized by Douglas Crockford in his lectures. Another piece of trivia is that if you've ever played with Yahoo's YUI library, some of its features may appear quite familiar and the reason for this is that the Module pattern was a strong influence for YUI when creating their components.

##### Example

```javascript
const myModule = (function() {
  // private variable
  const memes = ['cats', 'doge', 'harambe'];
    
  const getMemes = () => memes;
  
  // returns exactly what you want to give access to
  return {
    getMemes: getMemes
  };
})();

// examples
console.log(myModule.getMemes()); // (3) ["cats", "doge", "harambe"]
console.log(myModule.memes); // undefined
myModule.memes = 1;
console.log(myModule.memes); // 1
// you can't overwrite inner variable memes
console.log(myModule.getMemes()); // (3) ["cats", "doge", "harambe"]
```
