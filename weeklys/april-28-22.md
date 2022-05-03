# Fold An Array

### Problem

In this kata you have to write a method that folds a given array of integers by the middle x-times.

An example says more than thousand words:

```
Fold 1-times:

[1,2,3,4,5] -> [6,6,3]

A little visualization (NOT for the algorithm but for the idea of folding):

 Step 1         Step 2        Step 3       Step 4       Step5
                     5/           5|         5\          
                    4/            4|          4\      
1 2 3 4 5      1 2 3/         1 2 3|       1 2 3\       6 6 3
----*----      ----*          ----*        ----*        ----*

Fold 2-times:

[1,2,3,4,5] -> [9,6]
```
As you see, if the count of numbers is odd, the middle number will stay.
Otherwise the fold-point is between the middle-numbers, so all numbers would be added in a way.

The array will always contain numbers and will never be null.
The parameter runs will always be a positive integer greater than 0 and says how many runs of folding your method has to do.

If an array with one element is folded, it stays as the same array.

The input array should not be modified!

### Solution

Shot out to whoever did this at CoreCode, I couldn't really get it done without any hint of your solution, so thanks!

```js
function foldArray(array, runs) {
  
  if (runs === 0 || array.length === 1) {
    return array;
  }


  let result = [...array];
  let aheadPosition = 0;
  
  while (runs) {
    
    if (result.length === 1)  { return result; }
    result = Array.from(
      { length: Math.round(result.length / 2) },
      (v) => 0
    ).map((v, i) => {
      aheadPosition = result.length - (i + 1);
      if (aheadPosition === i) return result[i];
      return result[i] + result[aheadPosition];
    });
    
    runs--;
    
  }
  
  return result;

}
```

# Encrypt this!

### Problem

Encrypt this!

You want to create secret messages which can be deciphered by the Decipher this! kata. Here are the conditions:

1. Your message is a string containing space separated words.
2. You need to encrypt each word in the message using the following rules:
3. The first letter must be converted to its ASCII code.
4. The second letter must be switched with the last letter
5. Keepin' it simple: There are no special characters in the input.

```js
Examples:

encryptThis("Hello") === "72olle"
encryptThis("good") === "103doo"
encryptThis("hello world") === "104olle 119drlo"
```

### Solution

```js

// Arrow function: 

const encryptThis = (text) => {

 return text.split(' ').map((word) => {
 
    let [firstElement, ...rest] = word;
    
    let secondElement = rest.shift() || '';
    
    let lastElement = rest.pop() || '';
    
    return `${firstElement.charCodeAt(0)}${lastElement}${rest.join('')}${secondElement}`;
     
 }).join(' ');
 
}

// OR

// Inspired by CoreCode Solution

var encryptThis = function(text) {
  
  return text.split(' ').map( encryptText ).join(' ');
  
}


function encryptText( item ) {
  
  if (item.length === 1) { return item.charCodeAt(); }
  
  if (item.length === 2 ) { return `${item.charCodeAt(0)}${item[1]}`;  }
  
  return `${item.charCodeAt(0)}${item[item.length - 1]}${item.slice(2, item.length - 1)}${item[1]}`;
  
}
```

# Mission Statement

Hello, my name is Jonathan Juarez. I'am a Web Developer focused on Front End. I've been developing websites for almost 7 years now, using WordPress as CMS. I love create Custom Themes for WordPress that satisfy the clients needs. Althought mostly is Front-End, since is WordPress, I'm also familiar with PHP. My goal for this year is to get better at JavaScript, learn TypeScript and also React. I always try my best and always like to challenge myself to create really cool stuffs.
