# Constructor [⬈](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#constructorpatternjavascript)

### Description
In classical object-oriented programming languages, a constructor is a special method used to initialize a newly created object once memory has been allocated for it. In JavaScript, as almost everything is an object, we're most often interested in object constructors.

Object constructors are used to create specific types of objects - both preparing the object for use and accepting arguments which a constructor can use to set the values of member properties and methods when the object is first created.

### History
From a historical perspective, the Module pattern was originally developed by a number of people including Richard Cornford in 2003. It was later popularized by Douglas Crockford in his lectures. Another piece of trivia is that if you've ever played with Yahoo's YUI library, some of its features may appear quite familiar and the reason for this is that the Module pattern was a strong influence for YUI when creating their components.

### Example
The three common ways to create new objects in JavaScript are as follows:
```javascript
// Each of the following options will create a new empty object:
var newObject = {};
// or
var newObject = Object.create( Object.prototype );
// or
var newObject = new Object();
```

 JavaScript doesn't support the concept of classes but it does support special constructor functions that work with objects. By simply prefixing a call to a constructor function with the keyword "new", we can tell JavaScript we would like the function to behave like a constructor and instantiate a new object with the members defined by that function.
 ```javascript
 function Car( model, year, miles ) {
  this.model = model;
  this.year = year;
  this.miles = miles;
 
  this.toString = function () {
    return this.model + " has done " + this.miles + " miles";
  };
}

// We can create new instances of the car
var civic = new Car( "Honda Civic", 2009, 20000 );
var mondeo = new Car( "Ford Mondeo", 2010, 5000 );
 
// and then open our browser console to view the
// output of the toString() method being called on
// these objects
console.log(civic.toString()); // Honda Civic has done 20000 miles
console.log(mondeo.toString()); // Ford Mondeo has done 5000 miles
 ```