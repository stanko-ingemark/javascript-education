## 2. evenOddArgs

Write a function _evenOddArgs_ which returns an object whith two keys called _even_ and _odd_. Values of both those keys are arrays. _evenOddArgs_ should add every argument it received in one of these two arrays exactly once. If the argument was in even place, it should be added to the _even_ array. If it was in _odd_ place, it should be added to the _odd_ array.

__Examples__

```Javascript
console.log(evenOddArgs()) 
// output: {even: [], odd: []}

console.log(evenOddArgs("a")) 
// "a" is on the first (1.) place, so it's added to the "odd" array
// output: {even: [], odd: ["a"]}

console.log(evenOddArgs("a")) 
/* "a" is on the first (1.) place, so it's added to the "odd" array
/* output: {even: [], odd: ["a"]}

console.log(evenOddArgs("h", "e", "l", "l", "o")) 
// output: {even: ["e", "l"], odd: ["h", "l", "o]}

```