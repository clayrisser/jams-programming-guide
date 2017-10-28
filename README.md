# Jam's Programming Guide
An opinionated programming guide for consistent and collaborative programming

## Basic Constructs

### Functions

#### Use verbs for function names
##### INCORRECT :-1:
```js
function paymentForm() {
  // renders payment form
}
```

##### CORRECT :+1:
```js
function renderPaymentForm() {
  // renders payment form
}
```

## React

### Lifecycle Methods

#### Order lifecycle methods in the following order

* `constructor() {}`
* `componentWillMount() {}`
* `componentDidMount() {}`
* `componentWillUpdate() {}`
* `componentDidUpdate() {}`
* `renderSomeJSX() {}` // Custom render functions
* `render() {}`
* `handleSomeEvent() {}` // Event handlers
* `someHelperFunction() {}` // Helper functions
