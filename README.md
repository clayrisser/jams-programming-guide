# Jam's Programming Guide
An opinionated programming guide for consistent and collaborative programming

### The rule above all rules is consistency
For example, if the codebase does not end lines with semicolons, then don't end lines with semicolons

## Basic Constructs

### Use verbs for function names
#### INCORRECT :-1:
```js
function paymentForm() {
  // renders payment form
}
```
#### CORRECT :+1:
```js
function renderPaymentForm() {
  // renders payment form
}
```

## JavaScript

### Use single quotes for strings
#### INCORRECT :-1:
```js
const myString = "I am a string";
```
#### CORRECT :+1:
```js
const myString = 'I am a string';
```

### Use identity operator instead of equality operator
#### INCORRECT :-1:
```js
if ('1' != 1) {
  // this is false
}
```
#### CORRECT :+1:
```js
if ('1' !== 1) {
  // this is true
}
```

### End lines with semicolons
#### INCORRECT :-1:
```js
console.log('oops, I forgot a semicolon')
```
#### CORRECT :+1:
```js
console.log('yay, I have a semicolon');
```

### Use ES6 variable definitions
_Only follow this if ES6 is supported_
#### INCORRECT :-1:
```js
var hello = 'world';
```
#### CORRECT :+1:
```js
let hello = 'world';
```

### Avoid using alert boxes for debugging
It baffles me that people use `alert()` for debugging thier code,
but it happens frequently enough that I have to put this here. If you
need to debug your code, use `console.log()`.
#### INCORRECT :-1:
```js
alert('this is a super annoying message');
```
#### CORRECT :+1:
```js
console.log('this is much better');
```

### Avoid session storage on single page web applications
Single page web applications never get reloaded during a session,
so there's no reason to use sessionStorage. If you need global state,
use an in memory state machine like Redux.

## React

### Order lifecycle methods in the following order

* `constructor() {}`
* `componentWillMount() {}`
* `componentDidMount() {}`
* `componentWillUpdate() {}`
* `componentDidUpdate() {}`
* `renderSomeJSX() {}` _Custom render functions_
* `render() {}`
* `handleSomeEvent() {}` _Event handlers_
* `someHelperFunction() {}` _Helper functions_

### Avoid using the document object
You should avoid accessing the real dom
#### INCORRECT :-1:
```js
const myElement = document.getElementById('some-element');
```
If you must access the real dom, use refs
#### CORRECT :+1:
```js
const myElement = this.refs.someElement;
```

### Avoid using the jQuery library
Since jQuery is a library for manipulating the real dom, it should be avoided
