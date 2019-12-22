```javascript
function Parent() {}

function Child() {
  Parent.call(this);
  // ...
}

// Child() do not inherit methods defined in Parent()'s prototype, solution:

Child.prototype = Object.create(Parent.prototype);

Object.defineProperty(Child.prototype, 'constructor', {
  value: Child,
  enumerable: false,
  writable: true
});
```

4 types of property/method:
- Those defined inside constructor.
- Those defined directiry on constructor (static).
- Those defined on constructor's prototype.
- Those available on an object instance.

Inheritance with class syntax:
```javascript
class Child extends Parent {
  constructor(x) {
    // Old-school constructor functions: new operator does the initialization of this to a newly-allocated object.
    // This isn't automatically initiallized for a class defined by the extends keyword (i.e. subclasses).
    // For subclasses, the this initialization to a newly-allocated object is always dependant on the parent class.
    // In this case, the this initialization is done by the Parent constructor.
    super();  // 'this' is initialized by calling the parent constructor
    this._x = x;
  }
  
  get x() { return this._x; }
  
  set x(newX) { this._x = newX; }
}
```

Because of the way JavaScript works, with the prototype chain, etc., the sharing of functionality between objects is often called **delegation**.
