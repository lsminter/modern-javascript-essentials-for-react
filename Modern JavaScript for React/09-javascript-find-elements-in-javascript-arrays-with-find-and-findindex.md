To find a specific object in an array, we can use the find function on the array. We say array.find, and find takes a function which will get each item in the array.

```js
const spices = [
  { id: 1, name 'Black Pepper' },
  { id: 2, name 'Tumeric' },
  { id: 3, name 'Cumin' },
  { id: 4, name 'Coriander' },
  { id: 5, name 'Chili Powder' },
];

spices.find
```

Inside this `find` function, you want to return true if the item matches the one you want, and false otherwise. If we're looking for, say, coriander, we can say spice.name is coriander. The result of this call will be the first item that matched.

```js
spices.find(spice => {
  return spice.name === 'Coriander'
})
```

We could say const spice = this, and then we'll log out the spice. We can see we found it here. 

To print that out, we put it in a function: 

```js
const spice = spices.find(spice => {
  return spice.name === 'Coriander'
})
console.log(spice);
```

If we had a couple of them that each had, maybe different IDs, it will always print out the first one that it matches with. 

If you wanted to get the index of the item instead of the item itself, you can use findIndex. findIndex works the same way. It takes a function and you return true or false. It'll return the index of the first matching item. In this case, we get three.

```js
const spice = spices.findIndex(spice => {
  return spice.name === 'Coriander'
})
console.log(spice); // 3
```

For both find and findIndex, if you always return false, if you don't find a match, then you're going to get -1 for the findIndex case, or undefined if you're using find.