# Multiply Function Excercise

### Problem
```
function multiply(a, b){
 a * b
}
```
### Solution
```
function multiply(a, b) {
  return a * b;
}

------ or ------

const multiply = (a, b) => a * b;
```

# ASCII Total Excercise

### Problem
```
function uniTotal (string) {
// total up dem unicodes!
  
}
```
### Solution
```
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
```
function getChar(c){
  // ...
}
```

### Solution
```
function getChar(c){
  // ...
  return String.fromCharCode(c);
}

------- or ------

const getChar = c => String.fromCharCode(c);
```

# Binary Addition Excercise

### Problem
```
function addBinary(a,b) {

}
```

### Solution
```
function addBinary(a,b) {
  const sum = parseInt(a + b);
  return sum.toString(2)
}

------- or -------

const addBinary = (a, b) => parseInt(a + b).toString(2);
```

# Student's Final Grade Excercise

### Problem
```
function finalGrade (exam, projects) {
  return // final grade
}
```

### Solution
```
function finalGrade (exam, projects) {
  if (exam > 90 || projects > 10) return 100;
  if (exam > 75 && projects >= 5) return 90;
  if (exam > 50 && projects >= 2) return 75;
  return 0;
}
```
