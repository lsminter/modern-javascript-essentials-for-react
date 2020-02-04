You can use import and export to pull in code from other modules, whether those are from npm, Yarn, or your own code. Let's install the moment library by saying Yarn as moment.

Moment is a library for dealing with dates and times. We can import Moment from the string Moment. Once it's imported, we can call Moment in the format, the current date as year, month, day.

```js
import moment from 'moment';
console.log(moment().format('YYYY-MM-DD'));
```

What we've done here is import the default. Because it's the default, we could name it whatever we want, like M. That'll still work fine. Of course, the package name needs to match the one you installed. If it doesn't start with any path indicators like dots or anything, then it's usually going to be coming from node modules.

Let's install the lodash package. We'll run yarn add lodash. You could also run npm i lodash. Lodash is a useful utility library with a bunch of handy functions. One of them is called get. We can import get from lodash.

```js
import { get } from 'lodash';
```

We can create an object. If we call `get` on that object and git it a path, it will return us the last value of that path. 

```js
import { get as _get } from 'lodash';
const o = {
  a: {
    b: {
      c: 7
    }
  }
};
console.log(_get(o, 'a.b.c')); // 7
```

Get will resolve the string path by drilling into this object and pulling out the value. The great thing about get is that it returns undefined if it can't find that path. Versus if we try to access a.b.c directly, we get a reference error. 

The way we import get in this case is called a named import because it's inside braces. You can think of it like object destructuring, where this module is an object and we're pulling out a key called get and putting it in a variable called get.

This name needs to match the name in the module. If you want to rename it, you can use as and say, "rename get as *get."* 

```js
import { get as _get } from 'lodash';
```

To import everything from lodash you would use a *. 

```js
import * as _ from 'lodash';
```

Now we can use _.get because this variable underscore contains all the exports as keys. We can get oa.b.c. Remember, using star does need to be star as something. You can't just import everything into the current namespace. You can do star as whatever name you want and then use that name later on.

To import one of our own files, lets start by creating a new file called `user.js`. In here we will make a function that just returns the string "hi". 

To make this available to outside modules, we have to make sure to export it. 

```js
export default function sayHi() {
  console.log('hi');
}
```

Now if we call this in index.js after importing it, it works. 

```js
import sayHi from './user';
sayHi();
```

Just like with lodash, we can rename `sayHi` to anything we want in the import and it'll work just the same. 

Let's write another function called print name. It'll take a user object, and then log out the `user.firstname`, followed by `user.lastname`.

We already have one default export, and we can't have more than one of those. We could export this as a named export by just saying export function. Now, print name is a named export from this file. We could import that separately with the braces as print name from ./user. We can call our print name function and pass in a user object. That works well.

If we have another function in `user.js`, we can use a named export: 

```js
export function printName(user) {
  console.log(user.firstName, user.lastName);
}
```

We can also combine these into one import by putting the default import first, followed by a comma, and then any named imports. It has to be in this order, default followed by named. If we write it the other way, with named comma, default, we're going to get an error. 

```js
import hi, { printName } from './user';
```

You can export more than just functions. We can export variables as well. Keep in mind that your exports have to be on the top level of the file. They can't be inside of any blocks.