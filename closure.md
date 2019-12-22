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
