An easy way to add a number to the end of an array is to just use push. The problem with this is that it modifies the original array. 

To update it immutably, you would use concat instead. 

```js
const numbers = [1, 2, 3, 4];

numbers.concat(1000);
console.log(numbers); // ▶ (4) [1, 2, 3, 4]
```

It didn't change the original numbers array, but it did return a new one. If we log out the result of this, we can see we've got our new array with 1000 and then we haven't changed numbers.

```js
console.log(numbers.concat(1000)); // ▶ (5) [1, 2, 3, 4, 1000]
```

You can add a couple of items and it will stick all of them onto the end of the array. You can also pass in an entire array and it'll put them together into one flattened array. 

Another way you can do this is to make a new array and use the spread operator to spread out your first array, then spread out your second array. 

```js
console.log([...numbers, ...moreNumbers]); // ▶ (8) [1, 2, 3, 4, 5, 6, 7, 8]
```

You could also add stuff to the end, to the beginning, or in between. It'll combine all of that into one.

```js
console.log([0, ...numbers, 4.5, ...moreNumbers, 9]);
```