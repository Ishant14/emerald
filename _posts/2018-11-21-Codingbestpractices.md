# CodingBestPractices
This repositories contain the different coding best practices which i have learned by working in  different projects or by reading different books and blogs.


## Ternary operator

It will save you lines of code, very easily. This tip is working on almost all the modern languages and even older ones. The goal is to reduce a traditional if-else conditional statement into a one-liner.

**Common Way**

```javascript
let x = 3;

if(x > 1)
  console.log('X is above 1');
else 
  console.log('X is below 1');
  
// => X is above 1
```
**Ternary operator way**

```javascript
// First way
let x = 3;
let sentence = (x > 1) ? 'X is above 1':'X is below 1';
console.log(sentence);

// => X is above 1

// Second shorter way, less-readable
console.log( (x > 1) ? 'X is above 1':'X is below 1' ); // Without a temporary variable

// The syntax is always the same, no matter the language

// (conditional statement) ? result-if-true : result-if-false

// You can even chain the ternary operators

console.log( 
    (x > 1) ? 
      (x > 2) ? 'X is above 2':'X is below 2' 
      :'X is below 1'
  );

// => X is above 2

```

The point is :

-First, you get 4 lines turned into a one-liner not that hard to read.

-Second, it can be used in return statements because it is parsed as an expression.

-Finally, you can concatenate ternary operator expressions even if it’s not readable at all (You should refrain from doing it in production code).


## Logical negation operator

Lines of code saved, like always. But this time, readability will be improved ! What’s more ?

Let’s see how one would implement a basic light switch.

**Common Way**

```javascript
var lightPlugged = false;

function switchLight() 
{
  if(lightPlugged == false)
    lightPlugged = true;
  else 
    lightPlugged = false;
}

console.log( lightPlugged ? 'Light is on':'Light is off');
// => Light is off

switchLight();

console.log( lightPlugged ? 'Light is on':'Light is off');
// => Light is on

```

**Logical Negation Way**

```javascript
var lightPlugged = false;

function switchLight() 
{
  lightPlugged = !lightPlugged;
}

console.log( lightPlugged ? 'Light is on':'Light is off');
// => Light is off

switchLight();

console.log( lightPlugged ? 'Light is on':'Light is off');
// => Light is on
```

## String interpolation

String interpolation refers to the process of replacing programmer-defined keywords in a string with corresponding variables. It saves time, lines of code and readability.

**Old Way**

```javascript
let x = 5;
let expected = 8;

console.log('Content of variable x is: ' + x + ', and expected is ' + expected);

// => Content of variable x is: 5, and expected is 8
```

**String Interpolation way**

```javascript
let x = 5;
let expected = 8;

console.log(`Content of variable x is: ${x} and expected is ${expected}`);

// => Content of variable x is: 5, and expected is 8

```


## Functional programming basics - Map & Filter

Don’t worry, it will be dead-easy even if you’ve always been scared about functional programming.

Once again, it’s a language feature that a lot of languages support.

**Examples**

>Your first task is to double all the elements of an array.

**Old Way**

```javascript
let x = [1,2,3,4,5];
let y = [];

for(let i = 0; i < x.length; i ++)
  y[i] = x[i]*2;

console.log(y);

// => [2,4,6,8,10]
```

**Functional way with ES6 arrow functions**

```javascript
let x = [1,2,3,4,5];
let y = x.map ( element => element*2 );

console.log(y);

// => [2,4,6,8,10]

```

The map function loop through all the elements of an array and applies a function to each one. You just saved at least 2 lines of code, a for loop and a counter. Note that map improves readability (in my opinion).a

>Your second task is to implement the exact same algorithm, but doubling only the even numbers.

**Old Way**

```javascript
let x = [1,2,3,4,5];
let y = [];

for(let i = 0; i < x.length; i++)
  if(x[i] % 2 == 0)
    y.push(x[i]*2);
  else
    continue; 

console.log(y);

// => [4,8]
```

**Functional Way**

```javascript
let x = [1,2,3,4,5];
let y = x.filter( element => element % 2 == 0).map(element => element*2);

console.log(y);

// => [4,8]
```

The filter function loops through all the elements of an array and returns an array containing only the element matching the condition passed as parameter.





