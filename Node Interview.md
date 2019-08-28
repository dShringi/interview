## Node JS Interview

**Theory Questions**
- === vs == in JS
- use strict
- Closure in javascript
- NPM vs Node
- Package.json
- module.exports
- What Is The Difference Between Nodejs, AJAX, And JQuery?
- Implement nested functions as callbacks
- Implement async/await statements
- What is typically the first argument passed to a Node.js callback handler?
- How does Node.js handle child threads?
- What is “callback hell” and how can it be avoided?
- What is the preferred method of resolving unhandled exceptions in Node.js?
- How does Node.js support multi-processor platforms, and does it fully utilize all processor resources?
- What is worker threads
- What's the event loop?
- Child_Process Module
- Global and Local dependencies

-----------------------------------------------------------------------------------------
### Hands-on ###

Explain below code and implement the below using Promise or Async/Await.
```
const verifyUser = function(username, password, callback){
   dataBase.verifyUser(username, password, (error, userInfo) => {
       if (error) {
           callback(error)
       }else{
           dataBase.getRoles(username, (error, roles) => {
               if (error){
                   callback(error)
               }else {
                   dataBase.logAccess(username, (error) => {
                       if (error){
                           callback(error);
                       }else{
                           callback(null, userInfo, roles);
                       }
                   })
               }
           })
       }
   })
};
```
-----------------------------------------------------------------------------------------
```
console.log(sum(2,3));   // Outputs 5
console.log(sum(2)(3));  // Outputs 5
```
-------------------------------------------------------------------------------------------

### Output and Explanation

```
console.log("first");
setTimeout(() => {
    console.log("second");
}, 0);
console.log("third");
```
-----------------------------------------------------------------------------------------
```
null === "object"
```
-----------------------------------------------------------------------------------------
```
(function(){
  var a = b = 3;
})();

console.log("a defined? " + (typeof a !== 'undefined'));
console.log("b defined? " + (typeof b !== 'undefined'));
```
-------------------------------------------------------------------------------------------
```
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```
-------------------------------------------------------------------------------------------
```
function foo1()        function foo2()
{		       {
  return {                return
      bar: "hello"        {
  };                          bar: "hello"
}                          };
                       }
```                       
-------------------------------------------------------------------------------------------
```
(function() {
    console.log(1); 
    setTimeout(function(){console.log(2)}, 1000); 
    setTimeout(function(){console.log(3)}, 0); 
    console.log(4);
})();
```
-------------------------------------------------------------------------------------------
```
for (var i = 0; i < 5; i++) {
  var btn = document.createElement('button');
  btn.appendChild(document.createTextNode('Button ' + i));
  btn.addEventListener('click', function(){ console.log(i); });
  document.body.appendChild(btn);
}
(a) What gets logged to the console when the user clicks on “Button 4” and why?
(b) Provide one or more alternate implementations that will work as expected.
```
-------------------------------------------------------------------------------------------
```
var d = {};
…what is accomplished using the following code?

[ 'zebra', 'horse' ].forEach(function(k) {
	d[k] = undefined;
});
```
-------------------------------------------------------------------------------------------
```
var arr1 = "john".split('');
var arr2 = arr1.reverse();
var arr3 = "jones".split('');
arr2.push(arr3);
console.log("array 1: length=" + arr1.length + " last=" + arr1.slice(-1));
console.log("array 2: length=" + arr2.length + " last=" + arr2.slice(-1));
```
-------------------------------------------------------------------------------------------
```
console.log(1 +  "2" + "2");
console.log(1 +  +"2" + "2");
console.log(1 +  -"1" + "2");
console.log(+"1" +  "1" + "2");
console.log( "A" - "B" + "2");
console.log( "A" - "B" + 2);
```
-------------------------------------------------------------------------------------------
```
console.log(false == '0')
console.log(false === '0')
```
-------------------------------------------------------------------------------------------
```
var length = 10;
function fn() {
	console.log(this.length);
}

var obj = {
  length: 5,
  method: function(fn) {
    fn();
    arguments[0]();
  }
};

obj.method(fn, 1);
```
