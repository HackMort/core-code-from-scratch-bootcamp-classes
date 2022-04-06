# core-code-from-scratch-bc-class-1

## Interpreted and Compiled Languages

**Interpreted languages** Interpreters run through a program line by line and execute each command. They're usually significantly slower than compiled languages. But, with the development of just-in-time compilation (method for improving the performance of interpreted programs), the gap between compiled and interpreted languages is getting smaller. Examples: PHP, JavaScript.

**Compiled languages** usually are faster and more efficient than interpreted languages because they are directly converted into the machine. They also need to be build the first time and every time we want to make changes it needs to be rebuilt to reflect the new changes. Examples: C, C++.

## Is Java compiled or interpreted, or both?

A little bit of both... in other words it has a couple of stages that starts with the "compiled" to bytecode by a program called javac. Then moves to be interpretated by the Java Virtual Machine whichs translates the bytecode to machine code to be executed by the hardware. There's a really good screenshot that explains the cicle of java code. See below:

![Screenshot](https://i.stack.imgur.com/uQyXQ.png)


## Pseudocode Currency Converter

**Algorithm that will be used to convert dollars (USD) to bitcoin (BTC)**

```
  SYNTAX: 
  Starting point: START
  Input: READ, GET
  Output: PRINT
  Math: +, -, *, /
  Assignation: <--
  Initialize: SET, INIT
  Add one: INCREMENT
  End point: END
```

```
  SOLUTION:
  START 
  dollarsAmount <-- GET 
  btcCurrentPrice <-- 45,289.10 
  total <-- dollarsAmount * btcCurrentPrice 
  PRINT total 
  END
```

## High and Low level languages
**High Level:** Require the use of a compiler or an interpreter for their translation into the machine code.  
**Low Level:**  Require an assembler for directly translating the instructions of the machine language.  
