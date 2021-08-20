#JavaScript Important Question

Implementing Bing using Apply

```js
Function.prototype.myBind = function(){
  let context = arguments[0];
  let restArgument = Array.from(arguments);
  restArgument.shift();
  let fn = this
  console.log(fn);
  return function(){
    fn.apply(context,restArgument);
  }
}

// Example function
function b(middleName, otherName){
  console.log(this.name+' '+middleName+' '+otherName);
}

b.myBind();
```
