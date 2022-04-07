# Date of Birth in Binary

Date of Birth: 12-4-1989

```
12 / 2 = 6 -> 0
6 / 2 = 3 -> 0
3 / 2 = 1 -> 1
1 / 2 = 0 -> 1
------------------
Day (12) = 1 1 0 0
------------------
4 / 2 = 2 -> 0
2 / 2 = 1 -> 0
1 / 2 = 0 -> 1
-----------------
Month (4) = 1 0 0
-----------------
1989 / 2 = 994 -> 1
994 / 2 = 497 -> 0
497 / 2 = 248 -> 1
248 / 2 = 124 -> 0
124 / 2 = 62 -> 0
62 / 2 = 31 -> 0
31 / 2 = 15 -> 1
15 / 2 = 7 -> 1
7 / 2 = 3 -> 1
3 / 2 = 1 -> 1
1 / 2 = 0 -> 1
--------------------------------------------
Year of Birth (1989) = 1 1 1 1 1 0 0 0 1 0 1
--------------------------------------------
```

# MIPS Challenges

### Sum of two numbers

```
  .data
        message: .asciiz "\n.:: Sum of Two Numbers  ::.\n"
        total: .asciiz "\nResult is: "
        num1_message: .asciiz "\nNumber one: "
        num2_message: .asciiz "\nNumber two: "
  .text
        main:
              # message
              li $v0, 4
              la $a0, message
              syscall

              # user input
              li $v0, 4
              la $a0, num1_message
              syscall

              li $v0, 5
              syscall

              # saving user input
              move $t0, $v0

              # user input
              li $v0, 4
              la $a0, num2_message
              syscall

              li $v0, 5
              syscall

              # saving user input
              move $t1, $v0

              # adding the user numbers
              add $t2, $t0, $t1

              # show total
              li $v0, 4
              la $a0, total
              syscall

              # printing number
              li $v0, 1
              move $a0, $t2
              syscall
```

### Print My Name
```
  .data
	      name: .asciiz "\nJonathan Juarez (HackMort)\n"
  .text
	      main:
              li $v0, 4
              la $a0, name
              syscall
```
