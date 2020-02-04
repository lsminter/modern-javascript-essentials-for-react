If you have an array like this: 

```js
const people = [
  {
    first: 'Dan',
    last: 'Abramov',
    handle: '@dan_abramov'
  },
  {
    first: 'Ali',
    last: 'Spittel',
    handle: '@ASpittel'
  },
  {
    first: 'Sarah',
    last: 'Drasner',
    handle: '@sarah_edo'
  }
];
```

and we want it to pull out the first name from each person, we could use the map function on the array. If we wanted to extract the first name of each person, we can return person.first here and the result of this call as a map will be a brand new array made up of all of the first names. 

To extract the first name of each person, we return person.first. 

```js
people.map((person) => {
  return person.first
})
```

Map is a good function to use whenever you want a new array that has the same number of items as the old one. There's no way to exit early from a map call and there's no way to skip elements. If you want to skip certain items, you'll want to use filter instead.

The map function is also helpful if you want to change items in an array, but it's important to know that the items that get passed into this function actually are referring to the original items meaning if you change something, the original items will be changed.

A better way to do something like this where you want to update each item is to return a new item and copy in all the properties from person using the spread operator. Then you can change the first name to person.first + !!!. This changes the new array but doesn't touch the old one.

We can also get the index of the item and that's the second argument. If you need the index for something and you wanted to update maybe a specific item that has a specific index, that's available if you need it.