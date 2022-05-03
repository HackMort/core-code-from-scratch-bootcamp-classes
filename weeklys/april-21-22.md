# Remove All Exclamation Marks From The End Of Sentence

### Problem
Remove all exclamation marks from the end of sentence.
```js
Examples:

remove("Hi!") === "Hi"
remove("Hi!!!") === "Hi"
remove("!Hi") === "!Hi"
remove("!Hi!") === "!Hi"
remove("Hi! Hi!") === "Hi! Hi"
remove("Hi") === "Hi"
```

### Solution
```js
function remove(string) {
  const endOfString = string.length - 1;
  for (let i = endOfString; i > 0; i--) {
    if (string[i] !== '!') {
      string = string.substring(0, i + 1);
      break;
    }
  }
  return string;
}

// OR


// RegEx
const remove = (string) => string.replace(/!+$/, '');
```

# Remove vowels from a string

### Problem
Create a function called shortcut to remove the lowercase vowels (a, e, i, o, u ) in a given string.
```
Examples:

"hello"     -->  "hll"
"codewars"  -->  "cdwrs"
"goodbye"   -->  "gdby"
"HELLO"     -->  "HELLO"

** don't worry about uppercase vowels
** y is not considered a vowel for this kata
```

### Solution
```js
function shorcut(string) {
  return string.replace(/[aeiou]/gi, '');
}

// OR

const shortcut = (string) => string.replace(/[aeiou]/gi, '');
```

# Rock Paper Scissors!

### Problem
Let's play! You have to return which player won! In case of a draw return Draw!.
```js
Examples: 

rps('scissors','paper') // Player 1 won!
rps('scissors','rock') // Player 2 won!
rps('paper','paper') // Draw!
```

### Solution
```js
const rps = (p1, p2) => {
  
  if (p1 === p2) {
    return 'Draw!';
  }
  
  if (p1 === 'rock') {
    if (p2 === 'scissors') {
      return 'Player 1 won!';
    }
    return 'Player 2 won!';
  }
  
  if (p1 === 'paper') {
    if (p2 === 'rock') {
      return 'Player 1 won!';
    }
    return 'Player 2 won!';
  }
  
  if (p1 === 'scissors') {
    if (p2 === 'paper') {
      return 'Player 1 won!';
    }
    return 'Player 2 won!';
  }
  
};

// OR

// I really like this approach!

const rps = (p1, p2) => {
  const rulesObject = {
    'rock': 'scissors',
    'scissors': 'paper',
    'paper': 'rock'
  };
  if (p1 == p2) {
    return 'Draw!';
  }
  else {
    return 'Player ' + (rulesObject[p1] == p2 ? 1 : 2) + ' won!';
  }
};

```

# Persisten Bugger

### Problem
Write a function, persistence, that takes in a positive parameter num and returns its multiplicative persistence,
which is the number of times you must multiply the digits in num until you reach a single digit.
```
Examples: 

39 --> 3 (because 3*9 = 27, 2*7 = 14, 1*4 = 4 and 4 has only one digit)
999 --> 4 (because 9*9*9 = 729, 7*2*9 = 126, 1*2*6 = 12, and finally 1*2 = 2)
4 --> 0 (because 4 is already a one-digit number)
```
### Solution
```js
function persistence(num) {  
  const nums = num.toString().split('');  
  if (nums.length === 1) {
    return 0;
  }  
  let total = 1;  
  for (let i = 0; i < nums.length; i++) {
    total *= parseInt(nums[i]);
  } 
  return 1 + persistence(total);
}
```
