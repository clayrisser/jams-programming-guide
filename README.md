# Jam's Programming Guide
An opinionated programming guide for consistent and collaborative programming

![](assets/jams-programming-guide.png)

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

### Use nouns for variable and constant names
#### INCORRECT :-1:
```js
let run = true;
```
#### CORRECT :+1:
```js
let runner = true;
```

### Start boolean varaibles with `is`
#### INCORRECT :-1:
```js
let fast = true;
```
#### CORRECT :+1:
```js
let isFast = true;
```

### Ignore reduntant names
#### INCORRECT :-1:
```js
class Dog {
  dogBark() { console.log('woof'); }
}
```
#### CORRECT :+1:
```js
class Dog { 
  bark() { console.log('woof'); }
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
if ('1' == 1) {
  // this is true
}
```
#### CORRECT :+1:
```js
if ('1' === 1) {
  // this is false
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

### Use ES6 getters instead of get functions
_Only follow this if ES6 is supported_
#### INCORRECT :-1:
```js
class Dog {
  firstName = 'fido';
  lastName = 'brown';
  getName() {
    return `${firstName} ${lastName}`;
  }
}
```
#### CORRECT :+1:
```js
class Dog {
  firstName = 'fido';
  lastName = 'brown';
  get name() {
    return `${firstName} ${lastName}`;
  }
}
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

* `static someStaticProp = {}` _Custom static properties_
* `constructor() {}`
* `getChildContext() {}`
* `componentWillMount() {}`
* `componentDidMount() {}`
* `componentWillReceiveProps() {}`
* `shouldComponentUpdate() {}`
* `componentWillUpdate() {}`
* `componentDidUpdate() {}`
* `componentWillUnmount() {}`
* `handleSomeEvent() {}` _Event handlers_
* `someHelperFunction() {}` _Helper functions_
* `renderSomeJSX() {}` _Custom render functions_
* `render() {}`

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
