## 10. Retry 

Write a function _retry_ which accepts a single __function__ - _callbackCaller_ as an argument.  _callbackCaller_ accepts _callback_ as the last argument (same setup as previous example).

_retry_ returns a new __function__ _retryCallbackCaller_. It accepts the same arguments as _callbackCaller_ and attempts to do the same thing as  __callbackCaller__. If _callbackCaller_ would call _callback_ with the _result_, _retryCallbackCaller_ does the same. However, if _callbackCaller_ would call _callback_ with the _err_, _retryCallbackCaller_ waits one second (`setTimeout`), and repeats the call to the _callbackCaller_ with the same arguments. This time, it passes the _err_ or _result_ to _callback_ as they happen.


__Examples__

```Javascript
 const oddSeconds = (cb) => {
    const seconds = (new Date()).getSeconds();
    if (seconds % 2) cb(new Error("It's an odd second")); else cb(null, 'OK');
 }
 const retryOddSeconds = retry(oddSeconds);
 retryOddSeconds((err, result){
    if (err) console.log('ERROR: ', err.message);
    else console.log('RESULT: ', result);
 });
 
 /* Output (if called at odd second);
 ERROR: It's an odd second
 RESULT: OK
 */

/* Output (if called at even second);
 RESULT: OK
 */

```