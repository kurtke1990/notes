# Lesson1

## The Rule Of Functions
They should be small.
They should be smaller than that.
[Youtube](https://youtu.be/7EmboKQH8lM?t=3342)

## How small should function be ?
A function should **do one thing.**
[Youtube](https://youtu.be/7EmboKQH8lM?t=3358)

## "ONE THING" definition
If you cannot meaningfully extract another function from it.
[Youtube](https://youtu.be/7EmboKQH8lM?t=3520)

## Extracting process
[Youtube](https://youtu.be/7EmboKQH8lM?t=3760)

## Indenting
Smallness.
Functions should not be large enough to hold nested structures.
Therefore the indent level of function should not be greater than one or two.
[Youtube](https://youtu.be/7EmboKQH8lM?t=4144)

## How many arguments should a function have ?
Keep the number of arguments down to two or three.
Create objects or data structures If you have to use more than three arguments get into a function. 
[Youtube](https://youtu.be/7EmboKQH8lM?t=4237)

## What types of arguments should you mostly never pass into a function ?
**!!! BOOLEANS !!!**
Because if you pass a boolean into a function, there must be an If statement in that function.
Try to separate If statement into two functions, call the one in the true case, call the other in the false case.
[Youtube](https://youtu.be/7EmboKQH8lM?t=4372)

## Avoid Switch Statements
[Youtube](https://youtu.be/7EmboKQH8lM?t=4600)

## No Side-Effects
Side-Effect means a change to the state of system if you call a function and that function causes the system to change state then the function has a Side-Effect.
[Youtube](https://youtu.be/7EmboKQH8lM?t=5262)

## Command & Query Separation
A function returns void must have a side-effect. So if a function returns a value, it should not have side-effect.
Commands change the state of the system therefore they return void.
Anything returns a value by convention will not change the state of the system. It allows to keep the track of side-effect.
[Youtube](https://youtu.be/7EmboKQH8lM?t=5673)

## Pefer Exceptions To Returning Error Codes
[Youtube](https://youtu.be/7EmboKQH8lM?t=5736)

## Don't Repeat Yourself
[Youtube](https://youtu.be/7EmboKQH8lM?t=5831)

## Structured Programming
[Youtube](https://youtu.be/7EmboKQH8lM?t=5964)