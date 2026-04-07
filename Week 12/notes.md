# Week 12 - Functional Programming
Functional programming is widely used in backend development. It relates to all functional components of programming - working with arrays, lists, built-in functions, etc. Even in databases we use functional programming. 

Most modern programming languages support functional-style API declarations. 

## What is Functional Programming
In general, it treats computation as the evaluation of mathematical functions. It avoids changing state and mutable data. When creating a function, our main goal is to establish something which we are trying to achieve.

**Functions don't actually change data but might return new data.**

| Procedural | Declarative | Object-Oriented | Functional |
| --- | --- | --- | --- |
|Series of step-by-step instructions. C, Pascal, UNix shells | Describes WHAT you want, not HOW. SQL is a famouse example. | Objects with state + behaviour. Java, C++, Kotlin, Swift. | Functions as values. Functions have no side effects and data is immutable. |

Technically, all programming languages are procedural, in that they follow step by step instructions.

They are also primarily declarative, describing what yyou want rather than specifically how.

Functional Programming also supports Object-Oriented programming, with objects maintaining state and defining behaviours.

Functional Programming is supported by the majority of programming lnguages: Javascript, Python, Kotlin, Swift, Java, etc.

**In this course:**
We are primarily interested in functional-style APIs on collections--map, filter, reduce, etc. These exist in every modern language and replace verbose loops with elegant pipelines.

## 7 Principles of Functional Programming
1. First-Class Functions: functions which are used to produce values. They can be stored as variables, passed as arguments, and returned from other functions.
2. Deterministic (Pure) Functions: Same input always produces the same output, every single time
3. No Side Effects: Functions don't modify anything outside their own scope. There are no hidden state changes.
4. Immutable Data: Values never change after creation. New values are created instead of modifying old ones.
5. Declarative Style: Describe WHAT to compute, not HOW. Express operations as expressions, not step-by-step.
6. Function Composition: Combine small functions to build complex pipelines. Output of one feeds input of the next.
7. Recursion over loops: FP prefers recursive calls to for/while loops. Functions call themselves until a base case.

## Imperative vs. Functional Style
Imperative Style (How)

```javascript
const nums = [1,2,3,4,5,6,7,8];
let result = 0;

for (let i = 0; i < nums.length; i++>) {
    if (nums[i] % 2 === 0) {
        result += nums[i] * nums[i];
    }
}
```

Functional Style (What)
```javascript
const nums = [1,2,3,4,5,6,7,8];

const result = nums
    .filter(n => n % 2 === 0)
    .map( => n * n)
    .reduce((acc,n) => acc + n, 0);
```

## Pure Functions and Determinism
Pure:
```javascript
const add = (a,b) => a + b;
add(3,4);
```

Impure (side effect)
```javascript
let count = 0;
const inc = () => count++; // modifies external state
// inc() unpredictable if called from multiple places
```

Impure (relies on external state)
```javascript
let tax = 0.05;
const total = price => price + price * tax; // tax can change, output not predictable
```

#### What makes a function Pure?
- Same input always gets same output (deterministic)
- No side effects -- no I/O or global state mutation
- Does not depend on external mutable state
- Does not modify its input arguments
- Output is entirely determined by the return value

## Referential transparency & Lambda Expressions
**Referential Transparency:**
A function call can be replaced with its retun value without changing program behaviour. If add(3, 4) == 7, you can substitute 7 everywhere add(3, 4) appears.

Referentially Transparent:
```javascript
cost add(a,b) => a + b;
const result = add(3.4) + add(1,2);
// this is the same as 7 + 3 every time
```

Not Transparent:
```javascript
let x = 0;
const inc() => x++;
const result = inc() + inc() 
// this is not the same every time and cannot be functionally replaced with "1 + 2."
```

**Lambda / Anonymous Functions**
Lambda expressions create small, unnamed functions inline -- sesential for passing to map, filter, reduce, etc.