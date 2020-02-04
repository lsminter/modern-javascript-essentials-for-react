Immediate benefit is that it is shorter to type. 

```js
function makeFullName(first, last){
	return first + ' ' + last;
};
```
to

```js
const makeFullName = (first, last) => {
	return first + ' ' + last;
};
```

![](./pictures/Screen_Shot_2019-10-23_at_2.31.48_PM.png)

Another benefit is the explicit return. If you only have a single expression that return a value, you can shorten that up greatly. 

```js
const makeFullName = (first, last) => first + ' ' + last;
```
If the function returns nothing, it's the same as `return undefined`.

If it returns an object: 
```js
function createUser(name, email) {
	return {
		name: name,
		email: email,
		createdAt: Date.now()
	};
}
```
arrow function: 
```js
const createUser = (name, email) => {
	return {
		name: name,
		email: email,
		createdAt: Date.now()
	};
}
```
implicit function needs to be in parenthesis: 
```js
function createUser(name, email) => ({
		name: name,
		email: email,
		createdAt: Date.now()
	});
```
