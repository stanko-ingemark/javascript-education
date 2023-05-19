## 8. ensureCallbackArgument 

Write a function _ensureCallbackArgument_ which accepts one argument - a __function__ (_callbackCaller_). 
_callbackCaller_ receives any number and type of arguments (at least one), but the last one is a __function__ (_callback_) (by convention).

We want to make sure that every time _callbackCaller_ is called, it receives a _callback_ as the last argument (that is, we want to make sure that _callback_ is a function).

_ensureCallbackArgument_ returns a new function, which behaves exactly as _callbackCaller_. However, if the last argument to _callbackCaller_ is not a function, it throws an error ('Missing callback');

__Example__

```Javascript
const delayedAdd = (a,b, cb) => {
    setTimeout(() => {
        console.log('Calculating...');
        cb(null, a+b);
    }, 500);
}

const guardedDelayedAdd = ensureCallbackArgument(delayedAdd);

guardedDelayedAdd(3,2, (err, result) => {
    console.log('Result is ', result);
});

/*
Output (after half a second):
Calculating...
Result is 5
*/

guardedDelayedAdd(3,2,5);
/*
Output: immediately throws a 'Missing callback' error and nothing else
*/
```