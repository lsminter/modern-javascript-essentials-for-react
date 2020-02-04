If we create a variable called A and we set it equal to 1+2, the 1+2 is an expression. It's being assigned into A, but this entire thing is a statement.

```js
let a = 1 + 2
```

If you can put it on the right side of an equals sigh, its an expression. 

For statements, we have things like `if` blocks. 

Likewise, a `for` loop is also a statement. Same for `while`, and `try/catch`, and also `let` and `const` and `var`. 

Expressions that evaluate to a value can go on the right side of an equal sign, so things like math or an array or an object literal with keys and values. Things that can be assigned to variables or returned from functions.

Frameworks like React, the rule is that you can only have expressions inside JSX.

JSX lets you put expressions into curly braces. You can put things like math or strings, but you can't write statements like if or for.

Ok:
```js
function Component() {
	return <div>{"hi"}</div>
}
```

Not Ok: 
```js
function Component() {
	return <div>{for}</div>
}
```

For cases like this where you need to have an expression instead of a statement, you can rewrite some statements as expressions. 

If we need to rewrite this code as an expression, 

```js
if(Math.random() > 0.5) {
  a = 'yes'
} else {
  a = 'no'
}
```

We can use the ternary operator, which is the question mark. On the left side of the question mark goes the condition. In our case, this is the math.random. If this is true, then it's going to evaluate to the thing on the right which should be yes. Otherwise, use a colon to say that otherwise it'll evaluate to no.

```js
a = Math.random() > 0.5 ? 'yes' : 'no'
```

This entire thing is an expression and so we can use this anywhere we need an expression instead of a statement.