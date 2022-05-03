# Multiply Function Excercise

### Problem
```js
function multiply(a, b){
 a * b
}
```
### Solution
```js
function multiply(a, b) {
  return a * b;
}

// OR

const multiply = (a, b) => a * b;
```

# ASCII Total Excercise

### Problem
```js
function uniTotal (string) {
// total up dem unicodes!
  
}
```
### Solution
```js
function uniTotal (string) {
  let ascii = 0;
  for (let i = 0; i < string.length; i++) {
     ascii += string[i].charCodeAt();
  }
  return ascii;
}
```

# Char From ASCII Value Excercise

### Problem
```js
function getChar(c){
  // ...
}
```

### Solution
```js
function getChar(c){
  // ...
  return String.fromCharCode(c);
}

// OR

const getChar = c => String.fromCharCode(c);
```

# Binary Addition Excercise

### Problem
```js
function addBinary(a,b) {

}
```

### Solution
```js
function addBinary(a,b) {
  const sum = parseInt(a + b);
  return sum.toString(2)
}

// OR

const addBinary = (a, b) => parseInt(a + b).toString(2);
```

# Student's Final Grade Excercise

### Problem
```js
function finalGrade (exam, projects) {
  return // final grade
}
```

### Solution
```js
function finalGrade (exam, projects) {
  if (exam > 90 || projects > 10) return 100;
  if (exam > 75 && projects >= 5) return 90;
  if (exam > 50 && projects >= 2) return 75;
  return 0;
}
```
