# Even Numbers Solution:
I went a little ahead... 
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Even Numbers</title>
  <style>
    .grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-gap: 10px;
      grid-auto-rows: minmax(100px, auto);
    }
    .column {
      text-align: center;
    }
    ul {
      margin: 0;
      padding: 0;
      list-style-type: none;
    }
    .title {
      text-align: center;
    }
  </style>
</head>
<body>
  <h1 class="title">List of Even Numbers</h1>
  <div class="grid">
    <div class="column">
      <h1>For Loop</h1>
      <ul id="even-numbers-for"></ul>
    </div>
    <div class="column">
      <h1>While Loop</h1>
      <ul id="even-numbers-while"></ul>
    </div>
  </div>
  <script>
    
    const forList = document.getElementById('even-numbers-for');
    const whileList = document.getElementById('even-numbers-while');
    
    for (let i = 0; i <= 100; i++) {
      if (i % 2 === 0) {
        const li = document.createElement('li');
        li.textContent = i;
        forList.appendChild(li);
      }
    }
                            
                            
    let j = 0;
    while (j <= 100) {
      if (j % 2 === 0) {
        const li = document.createElement('li');
        li.textContent = j;
        whileList.appendChild(li);
      }
      j++;
    }
    
    
  </script>
</body>
</html>

```

# Bad Code
Bad code with comments explaining what the errors are:

```javascript

var cond = false;

if ((cond = true)) { // this evaluation is wrong it should be == or even better === to compare if the variable is true or false.
  console.log('The cond variable is true');
} else {
  console.log('The cond variable is false');
}

```
### Solution
```javascript
const cond = false;
if ( cond === true ) {
  console.log('The variable cond is true');
}
else {
  console.log('The variable cond is false');
}
```

# Bad Code 2

### Solution
```javascript

  const number = 100;
  if (number === 100) {
    console.log(`This is a special number!`);
  }
  else if (number < 1000 && number % 10 === 0) {
    console.log(`This number is almost special!`);
  }
  else {
    console.log(`Just a regular number!`);
  }

```
