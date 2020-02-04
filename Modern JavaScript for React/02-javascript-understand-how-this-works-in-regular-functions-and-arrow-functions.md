```js
'use strict';

function printThis() {
	console.log(this);
}

printThis(); // undefined
```

But if we bind a value and store that in a function: 

```js
const fn = printThis.bind(42)
fn(); // 42
```

`.call` won't force you to call the function again. It'll immediately call the function. `.apply` will also call the function immediately as long as its a regular function. 

But! if you do an arrow function, it doesn't work. 