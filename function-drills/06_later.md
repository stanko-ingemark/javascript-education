## 6. later 

Write a function _later_ which accepts two arguments - _delay_, which is a positive __integer__, and _fn_ which is a synchronous __function__. It should return a new __function__ _delayedFn_. 

_delayedFn_ accepts all of the same arguments as _fn_ plus one additional argument, _callback_, which is a __function__. When the _delayedFn_ is called, it first waits (_setTimeout_) for __delay__ miliseconds. After that, it calls the _fn_ with all the arguments it received (except _callback_). If the _fn_ was successful (no exceptions were thrown), it calls the _callback_ with _null_ as the first argument, and the result of the _fn_ as the second. If _fn_ raised an exception (_e_), it calls _callback_ with the _e_ as the first argument.

__Examples__

```Javascript
const divide = (a,b) => {
    if (b === 0) throw new Error('Division by zero');
    return a/b;
}

const delayedDivide = later(500, divide);
const cb = (err, result) => {
    if (err) {
        console.error('Error: ', e.message);
    } else {
        console.log('Result: ', result);
    }
}

delayedDivide(8,4, cb);
/* Output (after half a second):
Result: 2
*/

delayedDivide(3,0, cb);
/* Output (after half a second):
Error: Division by zero
*/

```