A **closure** gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

```javascript
function parent() {
  var x = 5;
  function child() {
    alert(x);  //  Nested functions have access to variables declared in their outer scope.
  }
  return child;
}

var myChild = parent();
myChild();  // alert 5

/* x would have been destroyed when parent finishes executing.

However JS forms closures = combination of function and environment 
within which that function was declared.

In this case, myChild is a reference to the instance of the function child,
the instance of child maintains a reference to its environment, within
which the variable x exists.
*/
```

Share environment:

```javascript
function parent() {
  var x = 5;
  return {
    child1: function() {..},
    child2: function() {..},
  };
}

// child1 and child2 refer to the same x
```

Closures have 3 scopes:
- Local scope
- Outer functions scope
- Global scope

```javascript
var e = 10;
function sum(a) {
  return function(b) {
    // e: global
    // b: outer functions
    // b: local
    return a + b + e;
  }
}
```
