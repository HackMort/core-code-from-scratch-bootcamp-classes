# Who Likes It?

### Problem

You probably know the "like" system from Facebook and other pages. People can "like" blog posts,
pictures or other items. We want to create the text that should be displayed next to such an item.

Implement the function which takes an array containing the names of people that like an item.
It must return the display text as shown in the examples:

```
[]                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
```

Note: For 4 or more names, the number in "and 2 others" simply increases.

### Solution

```
function likes(names) {
  const namesCount = names.length;
  if (namesCount === 0) {
    return `no one likes this`;
  }
  if (namesCount === 1) {
    return `${names[0]} likes this`;
  }
  if (namesCount === 2) {
    return `${names[0]} and ${names[1]} like this`;
  }
  if (namesCount === 3) {
    return `${names[0]}, ${names[1]} and ${names[2]} like this`;
  }
  return `${names[0]}, ${names[1]} and ${namesCount - 2} others like this`;
}

---------------- or -----------------

// I really like this one:

const likes = names => [
  'no one likes this',
  `${names[0]} likes this`,
  `${names[0]} and ${names[1]} like this`,
  `${names[0]}, ${names[1]} and ${names[2]} like this`,
  `${names[0]}, ${names[1]} and ${names.length - 2} others like this`
][Math.min(4, names.length)];

```

# Bit Counting

### Problem

Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number.
You can guarantee that input is non-negative.

Example: The binary representation of ```1234``` is ```10011010010```, so the function should return ```5``` in this case

### Solution

```
function countBits(n) {
  const number = n.toString(2);
  const array = number.split('');
  let count = 0;
  for (let i = 0; i < array.length; i++) {
    if (array[i] === '1') {
      count++;
    }
  }
  return count;
}
```

# Your order, please

### Problem
Your task is to sort a given string. Each word in the string will contain a single number.
This number is the position the word should have in the result.

Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).

If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.

#### Examples

```
"is2 Thi1s T4est 3a"  -->  "Thi1s is2 3a T4est"
"4of Fo1r pe6ople g3ood th5e the2"  -->  "Fo1r the2 g3ood 4of th5e pe6ople"
""  -->  ""
```

### Solution

```
function order(words){
  if (words === '') {
    return ''
  }
  const array = words.split(' ');
  const result = {};
  for (let i = 0; i < array.length; i++) {
    const word = array[i];
    const number = word.match(/\d+/g);
    result[number] = word;
  }
  const resultArray = [];
  for (let key in result) {
    resultArray.push(result[key]);
  }
  return resultArray.join(' ');
}

-------------- or -------------

function order(words){

 return words.split(' ').sort(function(a, b){
    return a.match(/\d/) - b.match(/\d/);
  }).join(' '); 

}
```
