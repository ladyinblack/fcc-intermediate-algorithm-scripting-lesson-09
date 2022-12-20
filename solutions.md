## ALTERNATE SOLUTIONS

### Solution 1
```js
function fearNotLetter(str) {
  for (let i = 0; i < str.length; i++) {
    /* code of current character */
    const charCode = str.charCodeAt(i);

    /* if code of current character is not equal to first character + no of iteration
        then a letter was skipped */
    if (charCode !== str.charCodeAt(0) + i) {
      /* if current character skipped past a character find previous character and return */
      return String.fromCharCode(charCode - 1);
    }
  }
  return undefined;
}

// test here
fearNotLetter("abce");
```

### Code Explanation
- This solution makes use of a `for` loop.
- Code of encountered character is stored in **code**.
- It is checked if code of current character is the expected one (no characters are skipped) by using the logic -- `code of current character = code of first character + number of iterations`.
- If a character is missing, the missing character is found and the final string is returned.
- `undefined` is returned if there is no missing character in the string.

### REFERENCE LINKS
- [JS For Loops Explained](https://www.freecodecamp.org/news/javascript-for-loops/)
- [String.length](http://forum.freecodecamp.org/t/javascript-string-length-javascript-length-explained-with-examples/19101)

### Solution 2
```js
function fearNotLetter(str) {
  let currCharCode = str.charCodeAt(0);
  let missing = undefined;

  str
    .split("")
    .forEach(letter => {
      if (letter.charCodeAt(0) === currCharCode) {
        currCharCode++;
      } else {
        missing = String.fromCharCode(currCharCode);
      }
    });

  return missing;
}

// test here
fearNotLetter("abce");
```

### Code Explanation
- First we define variables to store the character code for the first letter in the string, and to store whatever missing letter we may find.
- We turn the string to an array in order to `forEach` through it instead of using `for` and `while` loops.
- As we `forEach` through out letters' character codes, we go comparing with the one that should be in that position.
- If the current letter matches, we move the comparison variable to its next position so we can compare on the next cycle.
- If not, the missing letter will be assigned to the `missing` variable, which will be returned after the map is finished.
- If there are no missing characters, return `undefined`.

### REFERENCE LINKS
- [JS String Prototype `Split`](https://forum.freecodecamp.org/t/javascript-string-prototype-split-split-explained-with-examples/15944)

### Solution 3
```js
function fearNotLetter(str) {
  for (let i = 1; i < str.length; ++i) {
    if (str.charCodeAt(i) - str.charCodeAt(i - 1) > 1) {
      return String.fromCharCode(str.charCodeAt(i - 1) + 1);
    }
  }
}
```

### Code Explanation
- Loop over the string.
- Check if the difference in char codes between adjacent characters in the string is more than 1 (check ASCII table).
- Return the missing character (+1 from where the gap was detected).

```js
function fearNotLetter(str) {
  var allChars = "";
  var notChars = new RegExp("[^" + str + "]", "g");

  for (var i = 0; allChars[allChars.length - 1] !== str[str.length - 1]; i++)
    allChars += String.fromCharCode(str[0].charCodeAt(0) + i);

  return allChars.match(notChars)
    ? allChars.match(notChars).join("")
    : undefined;
}

// test here
fearNotLetter("abce");
```

### Code Explained
- A new string **allChars** is created.
- Create a regular expression **notChars** which selects everything except **str**.
- The `for` loop is used to add all the letters in the range to **allChars**.
- `match()` is used to strip off the **str** letters from the newly created string and it is returned.
- If there are no missing characters, returned `undefined`.

### REFERENCE LINKS
- [JS Regex Resources](http://forum.freecodecamp.org/t/regular-expressions-the-ultimate-list-of-learning-resources/15931)
- [JS Ternary](https://www.freecodecamp.org/news/ternary-operator-javascript-if-statement-tutorial/)
- [JS String Prototype Match](https://forum.freecodecamp.org/t/javascript-string-prototype-match-match-explained-with-examples/15941)
- [JS Array Prototype Join](https://forum.freecodecamp.org/t/javascript-array-join/568637)

