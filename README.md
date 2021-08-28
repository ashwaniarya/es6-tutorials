#JavaScript Important Question

Implementing Bind using Apply

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

Custom reduce pollyfill 
```js
Array.prototype.myReduce = function(callbackFn,initialValue){
  let self = this;
  let prevValue = initialValue
  for(let i = 0; i<self.length;i++){
    let newValue = callbackFn(prevValue,self[i],i)
    prevValue = newValue;
  }
  return prevValue;
}
```

Custom filter pollyfill
```js 
Array.prototype.myfilter = function(callbackFn, thisArg){
  let self = this;
  let newArray = [];
  for( let i = 0; i < self.length;i++){
    if(Boolean(callbackFn(self[i],i))){
      newArray.push(self[i]);
    }
  }

  return newArray;
}
```