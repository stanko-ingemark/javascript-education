## 5. randomCall 

Write a function _randomCall_ which receives an __array__ of __functions__ ([_fn1_, _fn2_, ...]) and returns a new __function__ (_randomCaller_). Each time _randomCaller_ is called, it calls one of the functions from the array _randomCall_ received ([_fn1_, _fn2_, ...]) with the arguments it (_randomCaller_) received.

__Examples__

```Javascript
const add = (a,b) => a+b;
const multiply = (a,b) => a*b;
const randomCallerAddMultiply = randomCall([add, multiply]);

randomCallerAddMultiply(3,2);
/*
Output: 5
or
Output: 6
(we don't know, it's random :) ) But we know it's one of the two.
*/

const add3 = (a,b,c) => a+b+c;
const multiply3 = (a,b,c) => a*b*c;
const randomCallerAdd3Multiply3 = randomCall([add3, multiply3, add2]);

randomCallerAdd3Multiply3(3,4,5);
/*
Output: 12
or
Output: 60
or
Output: 7
(again, who knows, random!)
*/
```
