# Articles
* [Let and const](#let-and-const)
* [React](#React)

# Let and const
Let and const are two different types of variables. Since [ES6](http://es6-features.org/#Constants) we no longer user `var` to define a variable but `let` and `const`.

## const
`const` is used to declare a variable which has a 'constant' value. This means that the value of a const variable can not be changed ones it's declared. **Usecase:**

HTML: 
```HTML
<div id='greeting'>Hello world!</div>
```
Javascript:
```Javascript
const greeting = document.getElementById('greeting');

greeting.style.color = 'red';
```

The value of the `const` variable: greeting is an HTML element, so it's logical that you can't reassign this variable. When doing some DOM manipulation in Javascript I've found that I use `const` most often. 

## let
`let` is used to declare a variable which has a value that can be reassigned. Like so:
```Javascript
let x = 1;
console.log(x); // output = 1

x = 2;
console.log(x); // output = 2

```

## Scope
Maybe the most important thing of `let` and `const` is that they are block-scoped. This means that when you define a let variable and then redefine it inside for example an if statement, both variables have a different scope. 
Example([MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)):
```Javascript
let x = 1;

if (x === 1) {
  let x = 2;

  console.log(x);
  // expected output: 2
}

console.log(x);
// expected output: 1
```
The same goes for `const` 

## var?
So what's the big difference with `var`? First of all, var says nothing about the variable itself. It's just an empty box where you can put a value in. With `const` you know it is a constant value and with `let` you know it is reassignable. 

Scoping with `var` is less strict than `const` and `let`, since const and let are block-scoped and var is function scoped. Example:
Because de variable is scoped by the function, the `console.log()` does'nt have acces to it. 
```Javascript
function changeValue() {
  var x = 1
}
console.log(x); // output x = undefined
```
Here variable x is declared in a block, but because it's a `var` it isn't scoped by the block and the console will log it. 
```Javascript
var y = true;

if(y) {
  var x = 2
}

console.log(x) // output x = 2
```

# React
## Why?
For the 'meesterproef' (final project of the minor), I'm working on a [project](https://github.com/Maikxx/360-wallscope) for [wallscope](https://wallscope.co.uk/) with three fellow students.
In this project we decided to work with the framework: 'React'.
Personnally I had never worked with React before, I knew it existed but had never touched it before this project. 

This will be an article about my view on react which is based on three weeks working with React. So I don't have a lot of experience with it. 

## Basics
React is a component based framework, which means that the entire app is put together by many different parts. Each part/component is made by one of the developers. 

### Pros
* The big advantage for our project is that it's easy to work on the same project as a team in a structured way. We have a [github project](https://github.com/Maikxx/360-wallscope/projects/1), where each task is put on the board. Anyone can pick a cord and start working on it. Mostly you'll make a new component and create a new feature branch for it in git. 
* Less merge conflicts. So if we use this workflow correctly, the amount of merge conflicts should be brought to a minimum. Because everyone creates their own branch for a component, once it's finished only they push it and create a pull request. So we're never working in each other's code. 
