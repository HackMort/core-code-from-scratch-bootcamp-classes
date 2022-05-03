# Holiday VIII - Duty Free

### Problem

The purpose of this kata is to work out just how many bottles of duty free whiskey you would have to buy such that the saving over the normal high street price would effectively cover the cost of your holiday.

You will be given the high street price (normPrice), the duty free discount (discount) and the cost of the holiday.

For example, if a bottle cost £10 normally and the discount in duty free was 10%, you would save £1 per bottle. If your holiday cost £500, the answer you should return would be 500.

All inputs will be integers. Please return an integer. Round down.
```js
function dutyFree(normPrice, discount, hol) {
  // Code
}
```

### Solution
```js
function dutyFree(normPrice, discount, hol) {
  
  const discPrice = ( normPrice * discount ) / 100;
  
  const numberOfBottles = hol / discPrice;
  
  const total = Math.floor(numberOfBottles);
  
  return total;
  
}

// OR

const dutyFree = (normPrice, discount, hol) => (
  Math.floor( hol / ( ( normPrice * discount ) / 100 ) ) 
)

```

# Twice as Old

### Problem

Your function takes two arguments:

1. current father's age (years)
2. current age of his son (years)
 
Сalculate how many years ago the father was twice as old as his son (or in how many years he will be twice as old).

```js
function twiceAsOld(dadYearsOld, sonYearsOld) {
  // your code here
}
```

### Solution
```js
function twiceAsOld(dadYearsOld, sonYearsOld) {
  const twiceAsOld = dadYearsOld - (sonYearsOld * 2);
  return Math.abs(twiceAsOld)
}

------------- or ------------

const twiceAsOld = (dadYearsOld, sonYearsOld) => Math.abs(dadYearsOld - (sonYearsOld * 2));
```

# Valid Spacing

### Problem
Your task is to write a function called valid_spacing() or validSpacing() which checks if a string has valid spacing. The function should return either true or false (or the corresponding value in each language).

For this kata, the definition of valid spacing is one space between words, and no leading or trailing spaces. Words can be any consecutive sequence of non space characters. Below are some examples of what the function should return:

### Solution
```js
function validSpacing(s) {
  // If is an empty string
  if (s.length === 0) {
    return true;
  }
  // If there's a space at the begining or the end of the string
  if (s[0] === ' ' || s[s.length - 1] === ' ') {
    return false;
  }
  // Creating an array based on a pattern of a single space.
  const newArray = s.split(' ');
  // Loop through the array.
  for (let i = 0;  i < newArray.length; i++) {
    if (newArray[i] === '') {
      return false;
    }
  }
  return true;
}
```

# Fake Binary

### Problem

Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.

Note: input will never be an empty string


```js
function fakeBin(x){

}
```

### Solution
```js
function fakeBin(x){
  
  let result = '';

  for (let i = 0; i < x.length; i++) {
    
    if ( parseInt(x[i]) < 5) {
      result += '0';
    }
    else if ( parseInt(x[i]) >= 5) {
      result += '1';
    }
    
  }
  
  return result;
  
}
```
