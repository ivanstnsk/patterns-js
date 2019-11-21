# Prototype [⬈](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#prototypepatternjavascript)

### Description
The GoF refer to the prototype pattern as one which creates objects based on a template of an existing object through cloning.

We can think of the prototype pattern as being based on prototypal inheritance where we create objects which act as prototypes for other objects. The prototype object itself is effectively used as a blueprint for each object the constructor creates. If the prototype of the constructor function used contains a property called name for example (as per the code sample lower down), then each object created by that same constructor will also have this same property.

Reviewing the definitions for this pattern in existing (non-JavaScript) literature, we may find references to classes once again. The reality is that prototypal inheritance avoids using classes altogether. There isn't a "definition" object nor a core object in theory. We're simply creating copies of existing functional objects.

Not only is the pattern an easy way to implement inheritance, but it can also come with a performance boost as well: when defining a function in an object, they're all created by reference (so all child objects point to the same function) instead of creating their own individual copies.

### Example
```javascript
var myCar = {
  name: "Ford Escort",
  drive: function () {
    console.log( "Weeee. I'm driving!" );
  },
  panic: function () {
    console.log( "Wait. How do you stop this thing?" );
  }
};
// Use Object.create to instantiate a new car
var yourCar = Object.create( myCar );
// Now we can see that one is a prototype of the other
console.log( yourCar.name ); // "Ford Escort"
```
