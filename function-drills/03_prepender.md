## 3. prepender

Write a function _prepender_ which accepts a single argument of type __string__ (let's call this _prependText_). It returns a new function (let's call this _prepend_). _prepend_ should also accept a single __string__ (_s2_) and return a __string__ which starts with _prependText_ and ends with _s2_.

__Examples__

```Javascript 
const prepend = prepender("My prefix >> ");
console.log(prepend("Hello!"));
// output: My prefix >> Hello!

```