## 7. callbackPerf 

Write a function _callbackPerf_ which accepts a single argument _callbackCaller_ which is a __function__ accepting a single argument - _callback_. It assumes _callbackCaller_ will call _callback_ with _err_ as the first argument (signifying some operation completed with error), or `null` as the first argument and _result_ as the second (signifying something was completed successfully). 

_callbackPerf_ returns a new __function__, _measuredCallbackCaller_ which behaves exactly as _callbackCaller_, but logs the timestamp (`Date.now()`) when the _callback_ is called, and the time which has passed (in milliseconds) when it was completed (with either _err_ or _result_);

__Examples__

```Javascript
const myCallbackCaller = (cb) => setTimeout(() => {
    cb(null, "I've been waiting one second for this");
}, 1000);
const myMeasuredCallbackCaller = callbackPerf(myCallbackCaller);
myMeasuredCallbackCaller((err, result) => {
    console.log(result);
})

/* Output:
Function called at: 1665339325394
Callback resolved in 1000 msecs.
"I've been waiting one second for this"
*/

```