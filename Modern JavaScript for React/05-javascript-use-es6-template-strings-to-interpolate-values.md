If we have a couple of strings and we wanted to concatenate them together into a full name, we can use ES6 template strings, which are the backticks, and these support string interpolations, so we can run expressions inside them by putting them inside dollar curly braces.

We can insert the first name, followed by a space, and then the last name. Log this out. Then we have our two strings put together.

```js
const firstName = 'Dave';
const lastName = 'Ceddia';
const usesReact = false;

const fullName = `${firstName} ${lastName}`; // Dave Ceddia
```

Because this is an expression, we could print out the full name, followed by some conditional text based on whether this person uses React. 

```js
const summary = `${fullName} ${usesReact ? 'uses React' : "doesn't use react"}`
```

We can log this out. Because this is false, we get doesn't-use-react. 

You can evaluate any valid JavaScript expression inside the curly braces. If we wanted to print, "The answer is 40 plus 2," and then log that out, we get, "The answer is 42."

```js
const answer = `The answer is ${40 + 2}`;
console.log(answer); // The answer is 42
```

We could even put a function in here. We would get the same thing because any valid JavaScript expression can go inside the curly braces. It'll evaluate that and put it into the string.