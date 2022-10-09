## 9. Timeout 

Write a function _timeout_ which accepts a single __function__ - _callbackCaller_ as an argument.  _callbackCaller_ accepts _callback_ as the last argument (same setup as previous example).

_timeout_ returns a new __function__ _timeoutCaller_ which behaves the same as _callbackCaller_. However, if _callbackCaller_ does not call back within 3 seconds, _timeoutCaller_ calls _callback_ with _err_, and it does not call _callback_ any more (regardless of what _callbackCaller_ does)

__Examples__

```Javascript
const timeoutSlow = timeout((cb) => {
    setTimeout(() => {
        cb(null, 'This took a long time');
    }, 5000);
});
timeoutSlow((err, result) => {
    if (err) console.log (err.message);
    else console.log(result);
});
// Output: TIMEOUT

const timeoutFast = timeout((cb) => {
    setTimeout(() => {
        cb(null, 'This was faster');
    }, 1000);
});

timeoutFast((err, result) => {
    if (err) console.log (err.message);
    else console.log(result);
});
// Output: This was faster

```