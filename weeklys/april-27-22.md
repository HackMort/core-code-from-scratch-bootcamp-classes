# Valid Parentheses

### Problem

Write a function that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return true if the string is valid, and false if it's invalid.

```
Examples

"()"              =>  true
")(()))"          =>  false
"("               =>  false
"(())((()())())"  =>  true
```

### Solution

```
function validParentheses(string) {
  let stack = [];
  for (let i = 0; i < string.length; i++) {
    if (string[i] === '(') {
      stack.push(string[i]);
    }
    else if (string[i] === ')') {
      if (stack.length === 0) {
        return false;
      }
      stack.pop();
    }
  }
  return stack.length === 0;

}
```

# Convert String To Camel Case

### Problem

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).

```
Examples

"the-stealth-warrior" gets converted to "theStealthWarrior"
"The_Stealth_Warrior" gets converted to "TheStealthWarrior"
```

### Solution

```
function toCamelCase(str) {
  let newString = '';
  let words = str.split(/[-_]/);
  for (let i = 0; i < words.length; i++) {
    if (i === 0) {
      newString += words[i];
      continue;
    }
    newString += words[i][0].toUpperCase() + words[i].slice(1);
  }
  return newString;
}

------------- or --------------

const toCamelCase2 = str => str.split(/[^a-z]/i).map((word, index) =>
                            index > 0 ? word.charAt(0).toUpperCase() + word.slice(1) : word).join('')
```

# Unique In Order

### Problem

Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.

```
For example:

uniqueInOrder('AAAABBBCCDAABBB') == ['A', 'B', 'C', 'D', 'A', 'B']
uniqueInOrder('ABBCcAD')         == ['A', 'B', 'C', 'c', 'A', 'D']
uniqueInOrder([1,2,2,3,3])       == [1,2,3]
```

### Solution

```
function uniqueInOrder(iterable) {
  if (iterable.length === 0) { return [] };
  let newArray = [];
  let current = iterable[0];
  for (let i = 1; i < iterable.length; i++) {
    if (iterable[i] !== current) {
      newArray.push(current);
      current = iterable[i];
    }
  }
  newArray.push(current);
  return newArray;
}

--------------- or-----------------
  
const uniqueInOrder = (iterable) => [...iterable].filter((a, i) => a !== iterable[i - 1]);
```
