The properties and methods are defined on the `prototype` property on the Objects' constructor functions, not the object instances themselves.

In JavaScript, a link is made between the object instance and its prototype by `__proto__` property.

`prototype` is a property containing an object on which you define members that you want to be inherited.

Every constructor function has a prototype property whose value is an object containing a `constructor` property. This constructor property points to the original constructor function.

Methods added to `Class.prototype` are then available on all object instances created from `Class()`.

Common pattern: define properties inside the constructor, methods on prototype.
