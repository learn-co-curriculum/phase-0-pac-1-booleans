# Boolean Expressions

## Learning Goals

- Explain What a Boolean Expression Is
- Describe Truthy and Falsey Values in JavaScript

## Introduction

Quite commonly in our computer programs, we want to execute code
_conditionally_, i.e., if some condition is true (or false). For example:

- _If_ the user has entered the correct login credentials, _then_ log them into
  our web app
- _If_ there isn't enough money in the user's account to execute the transfer,
  _then_ send them an error message

In the following lessons, we will learn about operators we can use to construct
those conditional statements. Before we get to that, however, we need to
understand _boolean expressions_ and the concepts of _truthy-ness_ and
_falsey-ness_.

## Explain What a Boolean Expressions Is

We have learned that _expressions_ are code statements that return a value: the
_constant expression_ returns the value of the constant, the _assignment
expression_ returns the value that is assigned, and the _variable lookup
expression_ returns the value of a variable. We have also learned that
JavaScript has a `Boolean` data type that has only two values: `true` or
`false`. As you might expect, therefore, a _Boolean expression_ is an expression
that returns either `true` or `false`.

## Describe the Difference Between Truthy and Falsey Values

All values in Javascript, of any data type (`String`, `Number`, etc.), are
treated as either _truthy_ or _falsey_. The following values are **falsey**:

- `false`
- `null`
- `undefined`
- `0`
- `NaN`
- An empty string (`""`, `''`)

**_Every other value is truthy_**.

To check whether a value is truthy or falsey, we can pass it to the global
`Boolean` object, which converts the value into its boolean equivalent. You may
want to try these out yourself in
[repl.it](https://repl.it/languages/javascript).

```js
Boolean(false);
// => false

Boolean(null);
// => false

Boolean(undefined);
// => false

Boolean(0);
// => false

Boolean(NaN);
// => false

Boolean("");
// => false

Boolean(true);
// => true

Boolean(42);
// => true

Boolean("Hello, world!");
// => true
```

Don't worry if this seems a little theoretical at this point. We will learn how
this information is used in constructing Boolean expressions in the following
lessons.

## Conclusion

In this lesson, we've learned what a _Boolean expression_ is. We've also learned
which values in JavaScript are considered _truthy_ and which are considered
_falsey_. With these understandings, we are now ready to learn how to construct
Boolean expressions that return `true` or `false`.

## Resources

- MDN
  - [Truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) and [falsey](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
