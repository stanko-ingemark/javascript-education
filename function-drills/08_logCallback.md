## 8. logCallback 

Write a function _logCallback_ which accepts one argument - a __function__ (_callbackCaller_). 
_callbackCaller_ receives any number and type of arguments (at least one), but the last one is a __function__ (_callback_).

We assume that _callbackCaller_, when called, attempts to do _something_. If it was succesfull, it will call back _callback_ with the _result_ of _something_ (for this example, we'll assume _result_ is a string) as a second argument - so, it will call `callback(null, result)`. If, on the other hand, _something_ was not successfull, _callbackCaller_ will execute a _callback_ with the _error_ (assume it's a string) as the first argument  - `callback(error)` (same as in the last two examples - this is, by convention, the standard form of callbacks in Javascript).

Now, our function, _logCallback_ should return a new __function__ (_loggedCallbackCaller_). It behaves the same as _callbackCaller_, excepts it
logs the arguments  it received, and  the argument _callbackCaller_ is passing to _callback_ (along with the information of wether it's a success or an error).

Very similar to (except without logging the arguments) [logFn](./04_logFn.md), but with callbacks.


__Example__

```Javascript
const myCallbackCaller = (today, cb) => {
    if (today == 'Friday') cb(null, "Jeey, it's Friday"); else cb("Still not Friday :(");
}

const loggedMyCallbackCaller = logCallback(myCallbackCaller);

loggedMyCallbackCaller('Friday', (err, result) => {
    if (!err) return console.log('Finally');
    console.log('Few more days left..');
});

/*
Output: 
Calling callback with the arguments: 'Friday'
Received callback success: "Jeey, it's Friday"
Finally
*/

loggedMyCallbackCaller('Monday', (err, result) => {
    if (!err) return console.log('Finally');
    console.log('Few more days left..');
});
/*
Output:
Calling callback with the arguments: 'Monday'
Received callback error: "Still not Friday :("
Few more days left..
*/

```