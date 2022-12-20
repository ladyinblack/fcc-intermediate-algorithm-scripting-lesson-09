# fcc-intermediate-algorithm-scripting-lesson-09

[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/js-svwbzf)

## PROBLEM EXPLANATION
You will create a program that will find the missing letter from a string and return it.  If there is no missing letter, the program should return undefined.  There is currently no test case for the string missing more than one letter, but if there was one, recursion would be used.  Also, the letters are always provided in order so there is no need to sort them.

### REFERENCE LINKS
- [String global object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- [JS String Prototype `CharCodeAt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)
- [`String.fromCharCode`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode) 

## HINTS
### Hint 1
You will need to convert from character to ASCII code using the two methods provided in the description.

### Hint 2
You will have to check for the difference in ASCII code as they are in order.  Using a chart would be very helpful.

### Hint 3
You will need to figure out where the missing letter is, along with handling the case that there is not missing letter as it needs a specific return value.

