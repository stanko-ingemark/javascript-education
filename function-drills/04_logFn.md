## 4. logFn

Write a function _logFn_ which accepts one argument which is a __function__ (let's call this _userFn_). It should return a new __function__ (let's call this _loggedUserFn_).
_loggedUserFn_ behaves exactly like _userFn_, except when it's called it logs arguments it received to console and before returning the value it also logs the value it returns to the console. 


__Examples__

```Javascript
const myFn = (a,b) => a+b;
const loggedMyFn = logFn(myFn);
console.log(loggedMyFn(3,2));
/*
Output:
Received arguments: 3,2
Return value: 5
5 
*/
```