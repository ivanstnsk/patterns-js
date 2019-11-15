# Singleton [⬈](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#singletonpatternjavascript)

### Description
The Singleton pattern is thus known because it restricts instantiation of a class to a single object. Classically, the Singleton pattern can be implemented by creating a class with a method that creates a new instance of the class if one doesn't exist. In the event of an instance already existing, it simply returns a reference to that object.

In JavaScript, Singletons serve as a shared resource namespace which isolate implementation code from the global namespace so as to provide a single point of access for functions.

### Example
```javascript
const Singleton = (function () {
  let instance;
 
  function init() {
    function privateMethod(){
        console.log("I am private");
    }
    const privateVariable = "Im also private";
 
    return {
      publicMethod: function () {
        console.log( "The public can see me!" );
      },
      publicProperty: "I am also public",
    };
  };
 
  return {
    getInstance: function () {
      if (!instance) {
        instance = init();
      }
      return instance;
    }
  };
})();

console.log(Singleton.getInstance());
console.log(Singleton.getInstance().publicProperty); // I am also public
```
