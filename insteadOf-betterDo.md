# JS instead of -> better do Best Practices

## Array Methods

```js
[3, 4, 5, 6].at(1); // 4
[3, 4, 5, 6].pop(); // [3, 4, 5)
[3, 4, 5, 6].push(7); // [3, 4, 5, 6, 7]
[3, 4, 5, 6].fill(1); // [1, 2, 1, 1]
[3, 4, 5, 6].join(" - "); // '3-4-5-6'
[3, 4, 5, 6].shift(); // [4, 5, 6]
[3, 4, 5, 6].unshift(1); // [1, 3, 4, 5, 6]
[3, 4, 5, 6].includes(5); // true
[3, 4, 5, 6].map((num) => num + 6); // [9, 10, 11, 12)
[3, 4, 5, 6].find((num) => num > 4); // 5
[{ id: 1, name: 'Apple' }].find(obj => obj.name === 'Apple'); // {id: 1, name: 'Apple'}
[3, 4, 5, 6].some((num) => num === 5); // true
[{ id: 1, name: 'Apple' }].some(obj => obj.name === 'Apple'); // true
[3, 4, 5, 6].filter((num) => num > 4); // [5, 6]
[3, 4, 5, 6].every((num) => num > 5); // false
[3, 4, 5, 6].findIndex((num) => num > 4); // 2
[3, 4, 5, 6].reduce((acc, num) => acc + num); // 18
[[3, 4, 5], [6]].flat(); // [3, 4, 5, 6]
[3, 4, 5, 6].flatMap((el) => [el, el * el]); // [3, 9, 4, 16, 5, 25, 6, 36]
[1, 2, 3, 4, 5].reduceRight((total, item) => total + item, 0); // 15
[1, 2, 3, 4, 5].fill(0); // [0, 0, 0, 0, 0]
[3, 4, 5, 6].reverse(); // [6, 5, 4, 3]
[{x:1},{x:2},{x:3}].reverse(); // [{x:3},{x:2},{x:1}]
"Hello".repeat(5); // 'HelloHelloHelloHelloHello'
["hello", "howdy", "Leo"].some((x) => "Leo, how do you do?".includes(x));  // true
"TechOnTheNet".startsWith("On", 4); // true
'Hello World!'.endsWith("World!"); // true 
5.56789.toFixed(1); // 5.6
['A','B','C','D','E'].map(letter => letter.charCodeAt(0)); // [65, 66, 67, 68, 69]
```

---

## for await...of

The for await...of statement creates a loop iterating over async iterable objects as well as sync iterables

---

## serialize an object to a URL

```js
let url = 'https://medium.com'
const query = {
  name: 'fatfish',
  age: 100,
}
url += '?' + Object.entries(query).map(([ key, value ]) => `${key}=${value}`).join('&')
```

---

## Map vs Object 

👉 Maps and objects are two commonly used data structures in programming languages, and both have their unique features and use cases. Understanding when to use a map vs an object can be a bit tricky, but this post will break down the differences and provide some guidance on when to use each.

✔️ An object is a collection of key-value pairs where each key must be a string or a symbol, and the value can be any data type. 

✔️ On the other hand, a map is a collection of key-value pairs where each key can be any data type, including objects and functions. Maps are useful when you need to store a large amount of data that is not necessarily related or when you need to quickly look up values based on a particular key. For example, you could use a map to store a list of customers and their order histories.

💡💡 So, when should you use a map vs an object? Here are some general guidelines:

💎 𝐔𝐬𝐢𝐧𝐠 𝐎𝐛𝐣𝐞𝐜𝐭𝐬 𝐟𝐨𝐫 𝐒𝐭𝐨𝐫𝐢𝐧𝐠 𝐚𝐧𝐝 𝐀𝐜𝐜𝐞𝐬𝐬𝐢𝐧𝐠 𝐑𝐞𝐥𝐚𝐭𝐞𝐝 𝐃𝐚𝐭𝐚:
Use an object when you need to store and access related data. For example, if you are building a system to manage employees, you might use an object to represent each employee, with properties such as name, age, and job title.

💎 𝐌𝐚𝐧𝐚𝐠𝐢𝐧𝐠 𝐋𝐚𝐫𝐠𝐞, 𝐔𝐧𝐫𝐞𝐥𝐚𝐭𝐞𝐝 𝐃𝐚𝐭𝐚 𝐰𝐢𝐭𝐡 𝐌𝐚𝐩𝐬:
Use a map when you need to store a large amount of data that is not necessarily related. For example, if you are building a system to manage a database of customer orders, you might use a map to store each order, with the order ID as the key and the order details as the value.

💎 𝐄𝐟𝐟𝐢𝐜𝐢𝐞𝐧𝐭 𝐃𝐚𝐭𝐚 𝐋𝐨𝐨𝐤𝐮𝐩 𝐰𝐢𝐭𝐡 𝐌𝐚𝐩𝐬:
Use a map when you need to quickly look up values based on a particular key. Maps are optimized for fast lookups, so they are ideal when you need to access data based on a specific key.

💎 𝐏𝐞𝐫𝐟𝐨𝐫𝐦𝐢𝐧𝐠 𝐃𝐚𝐭𝐚 𝐎𝐩𝐞𝐫𝐚𝐭𝐢𝐨𝐧𝐬 𝐰𝐢𝐭𝐡 𝐎𝐛𝐣𝐞𝐜𝐭𝐬:
Use an object when you need to perform operations on the data. Objects can have methods, which allow you to define functions that operate on the data stored in the object.

💡💡 In conclusion, both `maps` and `objects` have their unique features and use cases. Understanding when to use each depends on the specific requirements of your program. When in doubt, consider the nature of the data you need to store and how you will access it.

---

## Page Visibility API's `visibilityChange` 

> The Page Visibility API provides a way for web developers to determine whether a web page is currently visible to the user or hidden, such as when the user switches to another `tab` or `minimizes` the browser window. 

```js
document.addEventListener('visibilitychange', function() {
  if (document.hidden) {
    // The page is now hidden, such as when the user switches to another tab.
    // You can take some action when the page is not visible.
  } else {
    // The page is now visible again.
    // You can take some action when the page is visible.
  }
});
```


---

## Changing shape of objects inside arrays

```js
// Create array of numbers:
const records = [
  { name: 'Joe', grade: 'A' },
  { name: 'Tom', grade: 'B' },
  { name: 'Sandra', grade: 'B' },
  { name: 'Joel', grade: 'C' },
  { name: 'Victoria', grade: 'A' }
]

const updatedRecords = records.reduce((accumulator, currentItem) => {
  accumulator[currentItem.name] = {
    grade: currentItem.grade,
    passed: ['A', 'B'].includes(currentItem.grade)
  }
  return accumulator
}, {})


console.log(updatedRecords)
// {
//   Joe: { grade: 'A', passed: true },
//   Tom: { grade: 'B', passed: true },
//   Sandra: { grade: 'B', passed: true },
//   Joel: { grade: 'C', passed: false },
//   Victoria: { grade: 'A', passed: true }
// }
```

---

## Counting number of occurrences

```js
const fruit = ['apple', 'pear', 'lemon', 'avocado', 'apple', 'banana', 'pear', 'apple', 'pineapple'];

const occurrences = fruit.reduce((accumulator, currentItem) => {
  if (currentItem in accumulator) {
    accumulator[currentItem] = accumulator[currentItem] + 1
  } else {
    accumulator[currentItem] = 1
  }
  return accumulator
}, {})


console.log(occurrences); // {apple: 3,pear: 2,lemon: 1,avocado: 1, banana: 1,pineapple: 1 }
```

---

## output the `age` + quantity

```js
const user = [
    {name:'Tom', familyName: 'Lanese', age: 8},
    {name:'Leo', familyName: 'Lanese', age: 40},
    {name:'Carley', familyName: 'Lanese', age: 40}
]

const caca = user.reduce((acc, val) => {
    console.log(acc, val, acc[val.age]);
  
    if (acc[val.age]) {
      acc[val.age]++    
    } else {
      acc[val.age] = 1  
    }
    
    return acc
}, {})
```

---

## Remove min from Array

```js
const numbers = [1, 2, 3, 4, 5];

const min = numbers.reduce((acc, value) => acc < value ? acc : value) // 1

numbers.filter(value => value !== min) // [2, 3, 4, 5]
```

---

## Finding min & max values: MinMax

```js
const numbers = [1, 2, 3, 4, 5, 6];

// The callback function is called for each element in the array
// If the current `value` is less than the `acc` it returns value; otherwise, it returns acc.
const min = numbers.reduce((acc, value, i) => {
  return acc < value ? acc : value;
})

console.log(min) // 1
```

```js
const numbers = [1, 2, 3, 4, 5, 6];

const max = numbers.reduce((accumulator, currentValue) => {
  return accumulator > currentValue ? accumulator : currentValue;
})

console.log(max) // 6
```

---

## Summing values in an array

```js
const numbers = [1, 3, 5, 7, 9, 11];

const sum = numbers.reduce((accumulator, currentValue, index) => accumulator + currentValue, 0)

console.log(sum) // 36
```

---

## Find property in array of object and take it away

```js
const myArray = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" },
  { id: 3, name: "Charlie" },
];

const propertyToRemove = "name";

const newArray = myArray.filter(obj => !(propertyToRemove in obj));

console.log(newArray); // [{ id: 1 }, { id: 2 }, { id: 3 }]
```

---

## Find Indexes of All Occurrences of an Element in Array

```js
const arr = ["Nano", "Volvo", "BMW", "Nano", "VW", "Nano"]
  .reduce((acc, val, i) => {
    if (val === 'Nano')
      acc.push(i);
    return acc;
}, []);

console.log(arr); // [0, 3, 5]
```

---

### Convert an Array of Objects into One Object in JavaScript

```js
const arr = [{
  key: "11",
  value: "1100"
}, {
  key: "22",
  value: "2200"
}];
const object = arr.reduce((obj, item) => ({
  ...obj,
  [item.key]: item.value
}), {});

console.log(object); // {11: '1100', 22: '2200'}
```

---

## Get the last item in the list

```js
let array = [0, 1, 2, 3, 4, 5, 6, 7];

console.log(array.slice(-1)) >>> [7]; // [7]
```

---

### Falsy checks

```js
// instead of
// Long-hand
const isFalsey = (value) => {
  if (
    value === null ||
    value === undefined ||
    value === 0 ||
    value === false ||
    value === NaN ||
    value === ""
  ) {
    return true;
  }
  return false;
};

// better do
// Short-hand
const isFalsey = value => !!(value || value === 0);
```

---

## Ternary operator

```js
// instead of
// Long-hand
let info;
if (value < minValue) {
  info = "Value is too small";
} else if (value > maxValue) {
  info = "Value is too large";
} else {
  info = "Value is in range";
}

// better do
// Short-hand
const info =
  value < minValue
    ? "Value is too small"
    : value > maxValue ? "Value is too large" : "Value is in range";
```

---

### Get the last item in the list function

```js
let array = [0, 1, 2, 3, 4, 5, 6, 7];

function lastItem(list) {
  if (Array.isArray(list)) {
    return list.slice(-1)[0];
  }
  
  if (list instanceof Set) {
    return Array.from(list).slice(-1)[0];
  }
  
  if (list instanceof Map) {
    return Array.from(list.values()).slice(-1)[0];
  }
}

console.log(lastItem(array)); // 7
```

---

## Return after comparison

```js
// insteaf of
let test;
function checkReturn() {
  if (!(test === undefined)) {
    return test;
  } else {
    return callMe("test");
  }
}

// better do
function checkReturn() {
  return test ?? callMe("test");
}
```

---

## Default parameter value

```js
// insteaf of
function add(test1, test2) {
  if (test1 === undefined) test1 = 1;
  if (test2 === undefined) test2 = 2;
  return test1 + test2;
}

// better do
add = (test1 = 1, test2 = 2) => test1 + test2;
add(); //output: 3
```

---

## if (!response) return;

```js
this.buyTestService
  .submit(request)
  .pipe(first())
  .subscribe(
    (response: CardHolderName) => {
      if (!response) return;

      'isValid' in response
        ? this.validationSuccess.emit({ valid: true, name: request.cardHolderName })
        : (this.serverErrors = errorMessage);
    },
    (error: HttpError) => this.snackbarService.open(error.message),
  );
```

---

## Shorten console.log()

```js
const cl = console.log.bind(document) 
  cl(222) 
  cl("hello world")
```

---

## Use Objects For Function Arguments Instead Of Argument Lists

```js
// ❌ instead of 💩
function getItem(price, quantity, name, description) {}

getItem(15, undefined, 'bananas', 'fruit')

// better do
function getItem(args) {
    const { price, quantity, name, description } = args
}
getItem({
    name: 'bananas',
    price: 10,
    quantity: 1, 
    description: 'fruit'
})
```

---

## arguments object is not supported

```js
// ❌ instead of 💩
const fn1 = () => {
  console.log('arguments', arguments)
}
fn1('fatfish', 'medium'); // ERROR

// Better do ✅
function fn2(){
  console.log('arguments', arguments)
}
fn2('fatfish', 'medium');

// or even better ✅
const fn3 = (...values) => {
  console.log('values', values)
}
fn3('fatfish', 'medium')
```

---

## Implicit return using arrow function expressions. MB.

```js
// ❌ instead of 💩
function capitalize(name) {
  return name.toUpperCase()
}

function add(num1, num2) {
  return num1 + num2
}


// Better do ✅
const capitalize = (name) => name.toUpperCase()
const add = (num1, num2) => (num1 + num2)

// even better do
// Shorthand TypeScript (specifying variable type)
const capitalize = (name: string) => name.toUpperCase()
const add = (num1: number, num2: number) => (num1 + num2)
```

```js
// normal function definition
function add(a, b) {
  return (a + b)
}

// arrow syntax
const add = (a, b) => (a + b);
```

---

## get value from deep object or array

> Given an object or array — the function will return the value at specified path, otherwise null.

```js
const getValue = (obj, path) => {
  const properties = Array.isArray(path) ? path : path.split(".");
  return properties.reduce((prev, next) => prev?.[next], obj);
};

getValue({ a: { b: { c: 'd' } } }, 'a.b.c'); // 'd'
getValue({ a: { b: { c: [1, 2] } } }, 'a.b.c'); // [1,2]
```

---

###  Clamp

Ensure a value is within a specified range, otherwise "clamp" to the closest of the minimum and maximum value.

```js
const clamp = (min, max, value) => {
  if (min > max) throw new Error('min cannot be greater than max');
  return value < min
    ? min
    : value > max
      ? max
      : value;
}

clamp(0, 10, -5); // 0
clamp(0, 10, 20); // 10
```

---

### Group by, group value from deep object or array

Group and index related items in an object according to the keying-function.

```js
const groupBy = (fn, list) => (
  list.reduce((prev, next) => ({
    ...prev,
    [fn(next)]: [...(prev[fn(next)] || []), next]
  }), {})
);

groupBy(vehicle => vehicle.make, [
  { make: 'tesla', model: '3' },
  { make: 'tesla', model: 'y' },
  { make: 'ford', model: 'mach-e' },
]);

// { 
//   tesla: [ { make: 'tesla', ... }, { make: 'tesla', ... } ],
//   ford: [ { make: 'ford', ... } ],
// }
```

---

### Collect By

Create sub-lists containing related items according to the keying-function.

```js
import groupBy from './groupBy';

const collectBy = (fn, list) => 
  Object.values(groupBy(fn, list));

collectBy(vehicle => vehicle.make, [
  { make: 'tesla', model: '3' },
  { make: 'tesla', model: 'y' },
  { make: 'ford', model: 'mach-e' },
]);

// [ 
//   [ { make: 'tesla', ... }, { make: 'tesla', ... } ],
//   [ { make: 'ford', ... } ],
// ]
```

---

### Flatten

Create a flat list by pulling all items from nested sub-lists recursively.

```js
const flatten = list => list.reduce((prev, next) => ([
  ...prev,
  ...(Array.isArray(next) ? flatten(next) : [next])
]), []);

flatten([[1, 2, [3, 4], 5, [6, [7, 8]]]]); // [1, 2, 3, 4, 5, 6, 7, 8]
```

---

### Index By

Index each element in a list by a value determined by the keying-function.

```js
const indexBy = (fn, list) =>
  list.reduce((prev, next) => ({
    ...prev,
    [fn(next)]: next
  }), {});
              
indexBy(val => val.a, [{ a: 1 }, { a: 2 }, { a: 3 }]); 
// { 1: { a: 1 }, 2: { a:2 }, 3: { a: 3 } }
```

---

### Difference By. Difference between Array of Objects

Find all items in the first list that are not present in the second list — determined by the keying-function.

```js
const list1 = [{ make: 'tesla', year: 2022 }, { make: 'ford', year: 2021 }, { make: 'gm', year: 2023 }];
const list2 = [{ make: 'tesla', year: 2021 }, { make: 'bmw', year: 2022 }, { make: 'audi', year: 2023 }];

const keyingFunction = item => item.make;

const uniqueItems = list1.filter(item => !list2.some(otherItem => keyingFunction(otherItem) === keyingFunction(item)));

console.log(uniqueItems); // [{ make: 'ford', year: 2021 }, { make: 'gm', year: 2023 }]
```

---

### valid URL

```js
const isURL = (url) => {
  const regex = /(?:http(s)?:\/\/)?[\w.-]+(?:\.[\w\.-]+)+[\w\-\._~:/?#[\]@!\$&'\(\)\*\+,;=.]+/;
  return regex.test(url);
}
```

---

###  create an array of numbers from 1 to 10

```js
const array = [...Array(10).keys()].map(i => i + 1);
```

---

### create an object with all the properties and values of another object, but with a different key for each property

```js
const original = {a: 1, b: 2, c: 3};
const mapped = {...original, ...Object.keys(original).reduce((obj, key) => ({...obj, [key.toUpperCase()]: original[key]}), {})};
```

---

### verify credit card

```js
const isCreditCard = (cc) => {
  const regex = /(?:4[0-9]{12}(?:[0-9]{3})?|[25][1-7][0-9]{14}|6(?:011|5[0-9][0-9])[0-9]{12}|3[47][0-9]{13}|3(?:0[0-5]|[68][0-9])[0-9]{11}|(?:2131|1800|35\d{3})\d{11})/;
  return regex.test(cc);
}
```

---

### Ascending

Creates a ascending comparator-function given a valuating function.

```js
const ascending = (fn) => (a, b) => {
  const valA = fn(a);
  const valB = fn(b);
  return valA < valB ? -1 : valA > valB ? 1 : 0;
}

const byPrice = ascending(val => val.price);

[{ price: 300 }, { price: 100 }, { price: 200 }].sort(byPrice); 
// [{ price: 100 }, { price: 200 }, { price: 300 }]
```

---

### Declare empty object

```js
// eg1
One of the design goals of TypeScript is to "strike a balance between correctness and productivity." If it will be productive for you to do this, use Type Assertions to create empty objects for typed variables.

// ❌ instead of 💩
this.buyState.target.optionInterstitialScreen = {} as InfoInterstitialScreen;

// Better do ✅
this.buyState.target.optionInterstitialScreen = <InfoInterstitialScreen>{};
```

```js
// eg2
An `empty object` can be written as `Record<string,never>`, so effectively your type for user is either an empty object or a User

// ❌ instead of 💩
const user: User = {};

// Better do ✅
const user : User | Record<string, never> = {};
```

```js
// eg3
type User = {
    Username: string;
    Email: string;
}

const user01 = {} as User;
const user02 = <User>{};

user01.Email = "foo@bar.com";
```

---

### Use the default/optional parameters of the ES6 function

```js
// ❌ instead of 💩
const func = (name) => {
  name = name || "fatfish";
  console.log(name);
};

// Better do ✅
const func = (name = "fatfish") => {
  console.log(name);
};
```

---

### Simple template string replacement

```js
const formatString = (str: string, ...values: Array<string | number>) =>
  values.reduce(
    (s: string, v, i) => s.replace(new RegExp(`\\{${i}\\}`, "g"), String(v)),
    str
  );
const template =
  "My name is {0} and I am {1} years old. He is also {1} years old.";

console.log(formatString(template, "A", 35)); // My name is A and I am 35 years old. He is also 35 years old.
```

---

### Debugger 1. SHOW all DOM borders. Debugger trick. MB.

```js
// 1) cool
[].forEach.call($$("*"), (dom) => {
  dom.style.outline = "1px solid red";
});

// 2) even better
[].forEach.call($$("*"), (dom) => {
  dom.style.outline =
    "1px solid #" + (~~(Math.random() * (1 << 24))).toString(16);
});
```

---

### Debugger 2. SHOW all DOM borders. Debugger trick. MB

```js
(function () {
  var elements = document.body.getElementsByTagName("*");
  var items = [];
  for (var i = 0; i < elements.length; i++) {
    if (
      elements[i].innerHTML.indexOf(
        "* { background:#000!important;color:#0f0!important;outline:solid #f00 1px!important; background-color: rgba(255,0,0,.2) !important; }"
      ) != -1
    ) {
      items.push(elements[i]);
    }
  }
  if (items.length > 0) {
    for (var i = 0; i < items.length; i++) {
      items[i].innerHTML = "";
    }
  } else {
    document.body.innerHTML += "<style>* { border: 1px solid red;}</style>";
  }
})();
```

---

### Count number of array members

```js
const arr = [0, 1, 1, 2, 2, 2];

const count = arr.reduce((t, v) => {
  t[v] = t[v] ? ++t[v] : 1;
  return t;
}, {}); // { 0: 1, 1: 2, 2: 3 }
```

---

### Filter empty values (Interview question)

Empty values: undefined,null,"",0,false,NaN

```js
const arr = [undefined, null, "", 0, false, NaN, 1, 2].filter(Boolean); // [1, 2]
```

---

### Merge array (immutable trick)

```js
const arr1 = [0, 1, 2];
const arr2 = [3, 4, 5];

const arr = [...arr1, ...arr2]; // [0, 1, 2, 3, 4, 5];
```

---

### modify objects and arrays immutably

Objects and arrays are the reference types in javascript.
If we want to copy them into another object or an array and to modify them,
the best practice is to do that in an immutable way.

```js
// es6 spread operator
this.user = {
    name: 'Dzon',
    age: 25,
    address: 'Sunny street 34'
}

let updatedUser = {
    ...this.user,
    name: 'Peter'
}

//  spread operator with arrays
public results = [10, 12, 14];

let newNumbers = [...this.numbers, 45, 56];
```

---

### Executed when the object is not null

```js
const obj = { a: 0, b: 1, c: 2 };
Object.keys(obj).length && Func();
```

---

### Executed when the array is not empty

```js
const arr = [0, 1, 2];
arr.length && Func();
```

---

### removeUrlParameter

```js
function removeUrlParameter(url, param) {
  if (typeof URLSearchParams !== "undefined") {
    // modern browsers
    var r = new URL(url);
    r.searchParams.delete(param);
    return r.href;
  } else {
    // IE version
    return url
      .replace(
        new RegExp("^([^#]*?)(([^#]*)&)?" + parameter + "(=[^&#]*)?(&|#|$)"),
        "$1$3$5"
      )
      .replace(/^([^#]*)((\?)&|\?(#|$))/, "$1$3$4");
  }
}

removeUrlParameter(location.href, "comp");
```

---

### `URLSearchParams()` - URL query parameters:

> The URLSearchParams() constructor creates and returns a new URLSearchParams object.

> URLSearchParams() is specifically for dealing with query strings, not path segments. 

```js
// http://localhost:4200/en/?overlay=join
const urlParams = new URLSearchParams(window.location.href);
urlParams.has("overlay")); // true
```

```js
// The URLSearchParams interface defines utility methods to work with the query string of a URL.

const urlParams = new URLSearchParams("?post=1234&action=edit");

console.log(urlParams.has("post")); // true
console.log(urlParams.get("action")); // "edit"
console.log(urlParams.getAll("action")); // ["edit"]
console.log(urlParams.toString()); // "?post=1234&action=edit"
console.log(urlParams.append("active", "1")); // "?post=1234&action=edit&active=1"
```

```js
// .has()
const params = new URLSearchParams(location.search.replace(/\?/gi, ""));
params.has("test"); // true
params.get("sex"); // "man"

let url = new URL("https://example.com?foo=1&bar=2");
let params = new URLSearchParams(url.search);
params.has("bar") === true; //true

let url = new URL("https://example.com?foo=1&bar=2");
let params = new URLSearchParams(url.search);
params.has("bar") === true; //true
```

```js
// append()
let url = new URL("https://example.com?foo=1&bar=2");
let params = new URLSearchParams(url.search);

//Add a second foo parameter.
params.append("foo", 4);

console.log(params.getAll("foo")); // ["1","4"].
```

```js
var searchParams = new URLSearchParams("key1=value1&key2=value2");

searchParams.forEach(function (value, key) {
  console.log(value, key); // value1 key1, vakue2 key2
});
```

```js
// keys()
// Create a test URLSearchParams object
var searchParams = new URLSearchParams("key1=value1&key2=value2");

// Display the keys
for (var key of searchParams.keys()) {
  console.log(key); // key1, key2
}
```

```js
// values()
var searchParams = new URLSearchParams("key1=value1&key2=value2");

for (var value of searchParams.values()) {
  console.log(value); // value1,  value2
}

var searchParams = new URLSearchParams("key1=value1&key2=value2");
console.log(Array.from(searchParams.values())); // ['value1', 'value2']
```

```js
// build a new URL with an object of search parameters from an existing URL that has search parameters
const url = new URL("https://example.com/?a=hello&b=world");

console.log(url.href); // https://example.com/?a=hello&b=world
console.log(url.origin); // https://example.com

const add_params = {
  c: "a",
  d: new String(2),
  e: false.toString(),
};

const new_params = new URLSearchParams([
  ...Array.from(url.searchParams.entries()), // [["a","hello"],["b","world"]]
  ...Object.entries(add_params), // [["c","a"],["d","2"],["e","false"]]
]).toString();
console.log(new_params); // a=hello&b=world&c=a&d=2&e=false

const new_url = new URL(`${url.origin}${url.pathname}?${new_params}`);

console.log(new_url.href); // https://example.com/?a=hello&b=world&c=a&d=2&e=false
```

---

## Clear all cookies

```js
const clearCookies = document.cookie.split(';').forEach(cookie => document.cookie = cookie.replace(/^ +/, '').replace(/=.*/, `=;expires=${new Date(0).toUTCString()};path=/`));
```

---

## get value from cookie

```js
const getCookie = (name) => {
  const value = `; ${document.cookie}`;
  const parts = value.split(`; ${name}=`);
  if (parts.length === 2) return parts.pop().split(";").shift();
};
```


---

## Get the selected text

```js
const getSelectedText = () => window.getSelection().toString();
getSelectedText();
```

---

## Scroll to the top of the page

```js
const goToTop = () => window.scrollTo(0, 0);
goToTop();
```

---

## Calculate the interval between two dates

```js
const dayDif = (date1, date2) => Math.ceil(Math.abs(date1.getTime() - date2.getTime()) / 86400000)
    
dayDif(new Date("1975-04-22"), new Date("2023-01-24")); // 17444
```

---

## Determine whether the current tab is active

```js
const isTabInView = () => !document.hidden;
```

---

## if array is empty

```js
const arr = [];
const flag = Array.isArray(arr) && !arr.length; // flag => true
```

---

## Generate random id. Security generated value.

```js
const RandomId = (len) => Math.random().toString(36).substr(3, len);
const id = RandomId(10); // id => "xdeguewg1f"
```

---

## Generate star ratings

```js
const StartScore = (rate) => "★★★★★☆☆☆☆☆".slice(5 - rate, 10 - rate);
const start = StartScore(3);
```

---

## Check if Object is Empty

```js
// Option 1
// null and undefined using constructor check
const isEmptyObject = (obj) => {
  return obj 
  	&& Object.keys(obj).length === 0 
		&& obj.constructor === Object;
};

isEmptyObject(new String()); // false ✅
isEmptyObject(new Number()); // false ✅
isEmptyObject(new Boolean()); // false ✅
isEmptyObject(new Array()); // false ✅
isEmptyObject(new RegExp()); // false ✅
isEmptyObject(new Function()); // false ✅
isEmptyObject(new Date()); // false ✅

isEmptyObject(100);  // false ✅
isEmptyObject(true); // false ✅
isEmptyObject([]);   // false ✅

isEmptyObject(null); // null ✅
isEmptyObject(undefined); // undefined ✅
```

```js
// Option 2
// legacy browsers
const isEmptyObject = (objectName) => {
  return Object.prototype.toString.call(value) === '[object Object]'  
    && JSON.stringify(objectName) === "{}";
};

console.log(isEmptyObject(emptyObject)); // true
```

---

## Search key exist and parse it

```js
this.transferOptions = [{}]

private initInterstitialScreen(transferOptions: TransferOptions): void {
  transferOptions.targets.find((target) => {
    if (target.optionInterstitialScreen !== undefined) {
      this.screenConfig = target.optionInterstitialScreen;
    }
  });
}

this.initInterstitialScreen(this.transferOptions);
```

---

## Removes the trailing slash of a string

```js
const removeTrailingSlash = (value: string): string =>
  value && value.charAt(value.length - 1) === "/" ? value.slice(0, -1) : value;

removeTrailingSlash("foo-bar/"); // foo-bar
```

---

## Decapitalize a string

```js
const decapitalize = (str: string): string =>
  `${str.charAt(0).toLowerCase()}${str.slice(1)}`;

decapitalize("Hello world"); // hello world
```

---

## Generate a random number string based on the current time.

```js
const randomNumberString = (): string =>
  new Date().getTime() + Math.random().toString(36).slice(2);

randomNumberString(); // 1646617484381wml196a8iso
```

---

## Generates a random integer based on current time

```js
const randomInteger = (): number => new Date().getTime();

randomInteger(); // 1646617367345
```

---

## Toggling a boolean. Turning a false to true and a true to false.

```js
const toggleBoolean = (val: boolean): boolean => (val = !val);

toggleBoolean(true); // false
```

---

## Convert NodeList to a real array

```js
// $divs is a NodeList
const $divs = document.querySelectorAll('div')
// $arrayDivs is An Array
const $arrayDivs = [ ...$divs ]
console.log(Array.isArray($divs), Array.isArray($arrayDivs)) // false true
```

---

## Converts a string into a words separated by '-'

```js
const slugify = (str: string): string =>
  str
    .toLowerCase()
    .replace(/\s+/g, "-")
    .replace(/[^\w-]+/g, "");

console.log(slugify("Hello World Leo Lanese")); // "hello-world-leo-lanese"
```

---

### Capitalize string.

```js
const capitalize = (s: string): string =>
  s.charAt(0).toUpperCase() + s.slice(1);

capitalize("lorem ipsum"); // Lorem ipsum
```

---

### Check if an array is empty.

```js
const isArrayEmpty = (arr: unknown[]): boolean =>
  Array.isArray(arr) && !arr.length;

isArrayEmpty([]); // true
isArrayEmpty([1, 2, 3]); // false
```

---

###  Check if an object/array is empty.

```js
const isObjectEmpty = (obj: unknown): boolean =>
  obj && Object.keys(obj).length === 0;

isObjectEmpty({}); // true
isObjectEmpty({ foo: "bar" }); // false
```

---

###  Generating a random integer based on two arguments.

```js
const randomInteger = (min: number, max: number): number =>
  Math.floor(Math.random() * (max - min + 1)) + min;

randomInteger(1, 10); // 7
```

---

###  Generating a random boolean

```js
const randomBoolean = (): boolean => Math.random() >= 0.5;

randomBoolean(); // true
```

---

### wait / sleep

```js
const wait = (ms: number): Promise<void> =>
  new Promise((resolve) => setTimeout(resolve, ms));

await wait(1000); // waiting 1 second
```

---

### Day notation of the week notation

```js
const isWeekday = (d: Date): boolean => d.getDay() % 6 !== 0;

isWeekday(new Date(2022, 2, 21)); // true
isWeekday(new Date(2021, 2, 20)); // false
```

---

### Revers. Reversing a string with words

```js
const reverse = (s: string): string => s.split("").reverse().join("");

reverse("elon musk"); // -> 'ksum nole'
```

---

#### Rotate. Reverse Array of string

```js
var fruits = ["Banana", "Orange", "Apple", "Mango"];

fruits.reverse(); // ["Mango", "Apple", "Orange", "Banana"]
```

---

#### reverse string  

```js
// e1g
const reverse = (str) =>
  str
    .split(" ")
    .map((word) => word.split("").reverse().join(""))
    .reverse()
    .join(" ");

reverse("Argument goes here"); // ereh seog tnemugrA
```

```js
// eg2
const reverseString = (string) => [...string].reverse().join("");

reverseString("Leo"); // oeL
```

---

### Check if a number is even & odd

```js
const isEven = (n: number): boolean => n % 2 === 0;

isEven(2); // true
isEven(3); // false
```

```js
function isEven (number) {
  return (number & 1) === 0;
}
```

```js
//check if the number is odd
function isOdd (number) {
  return (number & 1) === 1;
}
```

---

### Count quantity/appereances/repetirions elements in an array

```js
const myFruits = [
  "Apple", "Orange", "Mango", "Banana", "Apple", "Apple", "Mango",
];

// first option
const countMyFruits = myFruits.reduce((countFruits, fruit) => {
  countFruits[fruit] = (countFruits[fruit] || 0) + 1;
  return countFruits;
}, {});
console.log(countMyFruits); // { Apple:3, Banana:1, Mango:2, Orange:1 }
```

```js
const myFruits = [
  "Apple", "Orange", "Mango", "Banana", "Apple", "Apple", "Mango",
];

// second option
const fruitsCounter = {};

for (const fruit of myFruits) {
  fruitsCounter[fruit] = fruitsCounter[fruit] ? fruitsCounter[fruit] + 1 : 1;
}
console.log(fruitsCounter); // { Apple:3, Banana:1, Mango:2, Orange:1 }
```

---

### Search value inside array: find()

```js
const targetAccountIdActive = !!this.transferOptions.sources.find(
   x => x.accountId ==='target_account_id',
) as boolean;
```

---

### Check if a Array is empty. Nested validation.

```js
let myArray = [1, 245, "apple", { type: "fruit" }];

myArray.length; // 4
myArray?.length ? true : false; // true
myArray && myArray.length ? true : false; // true
```

```js
let myArray2 = [1, 245, "apple", { type: "fruit" }];

myArray2?.[3]?.type ?? "No type property"; // 'fruit'
```

```js
// isArray() method
let myArray = [1, 245, "apple", { type: "fruit" }];

Array.isArray(myArray); // true
```

---

### Optional chaining: '?.'

```js
// Rules Optional chaining
obj.val?.prop;
obj.val?.[expr];
obj.arr?.[index];
obj.func?.(args);
```

---

### Optional chaining: '?.'

```js
const user = {
  name: 'Leo',
  address: {
    street: 'Washington 560',
    city: 'Rosario',
  },
};

const street = user?.address?.street; // "Washington 560"
const zipCode = user?.address?.zipCode; // undefined
```

---

### Optional chaining pn try/catch: '?.'

```js
// ❌ instead of 💩
function doSomething(onContent, onError) {
  try {
    // ... do something with the data
  } catch (err) {
    if (onError) {
      // Testing if onError really exists
      onError(err.message);
    }
  }
}

// better do ✅
// Using optional chaining with function calls
function doSomething(onContent, onError) {
  try {
    // ... do something with the data
  } catch (err) {
    onError?.(err.message); // no exception if onError is undefined
  }
}
```

```js
const streetName = user && user.address && user.address.street.name;
const streetName = user?.address?.street?.name;
// this will run even if options is undefined (in which case, onSuccess would be undefined as well)
// however, it will still fail if options was never declared,
// since optional chaining cannot be used on a non-existent root object.
// optional chaining does not replace checks like if (typeof options == "undefined")
const onSuccess = options?.onSuccess;
// this will run without error even if onSuccess is undefined (in which case, no function will be called)
onSuccess?.({ data: "yay" });
// and we can combine those things into a single line:
options?.onSuccess?.({ data: "yay" });
// and if you are 100% certain that onSuccess is a function if options exists
// then you don't need the extra ?. before calling it. Only use ?. in situations
// where the thing on the left might not exist.
options?.onSuccess({ data: "yay" });
// in React:
function UserProfile({ user }) {
  return (
    <div>
      <h1>{user.name}</h1>
      <strong>{user.bio?.slice(0, 50)}...</strong>
    </div>
  );
}
```

---

## use a more declarative code

```js
//  instead of
// index1.js
if (status === 1 || status === 2) {
  // ...
} else if (status === 3) {
  // ...
}

// index2.js
if (status === 1 || status === 2) {
  // ...
}


// better do
const STATUS = {
  // It is an adult and has real-name authentication
  adultRealName: 1,
  // It is a minor and has real-name authentication
  minorRealName: 2,
  // Not real-name authentication
  notRealName: 3,
  // ...
}

// index1.js
if ([ STATUS.adultRealName, STATUS.minorRealName ].includes(status)) {
  // ...
} else if (status === STATUS.notRealName) {
  // ...
}
// index2.js
if ([ STATUS.adultRealName, STATUS.minorRealName ].includes(status)) {
  // ...
}
```

---

## Remove call back hell

```js
// instead of
fetch('/a')
  .then((a) => {
    fetch('/b', { a })
      .then((b) => {
        fetch('/c', { b })
          .then((c) => {
            console.log(c)
          })
      })
  })


// better do
const a = await fetch('/a')
const b = await fetch('/b', { a })
const c = await fetch('/c', { b })

console.log(c); //
```

---

### reduce parameters to the function

```js
// instead of
const getUser = (name, weight, mobile, gender, address, hobby, ...) => {
  // ...
  return ...
}

getUser('fatfish', 100, 183, ....); //


//better do
const getUser = (options) => {
  const { name, weight, mobile, gender, address, hobby, ... } = options
  // ...
  return ...
}

getUser({
  name: 'fatfish',
  weight: 100,
  mobile: 183
  ...
}); // 
```

---

### Operate values array. Total Ammount

```js
// eg1
const amounts = [10, 30, 40, 50];

let total - 0; 2 let total - 0;
for (let num of amounts) {
  total += num; total += num;
}
```

```js
// eg2
const amounts = [10, 30, 40, 50];

let total = 0;
amounts.forEach((num) => {
  total += num;
});
```

```js
// eg3
const amounts = [10, 30, 40, 50];
const total = amounts.reduce((x, y) => x + y);
```

---

### Modify objects and arrays iwth immutability by spread operator

```js
// spread operator objects
this.user = {
  name: "Dzon",
  age: 25,
  address: "Sunny street 34",
};
// {name: 'Dzon', age: 25, address: 'Sunny street 34'}

let updatedUser = {
  ...this.user,
  name: "Peter",
}; // {name: 'Peter', age: 25, address: 'Sunny street 34'}

// but previous Object conservs immutability
// user {name: 'Dzon', age: 25, address: 'Sunny street 34'}
```

---

## Template Literal Types

```js
type EventNames2 =
    'onMessageCreated' |
    'onMessageUpdated' |
    'onMessageDeleted' |
    'onFolderCreated' |
    'onFolderUpdated' |
    'onFolderDeleted' |
    'onFileCreated' |
    'onFileUpdated' |
    'onFileDeleted';

type EntityType = 'Message' | 'Folder' | 'File' | 'NewEntity';
type EventOperations = 'Created' | 'Updated' | 'Deleted';

type EventNames = `on${EntityType}${EventOperations}`;
```

---

## Check/Validate if an Object has a Specific Property

```js
// hasOwnProperty method
const obj = {
  a: 1,  b: 2,  c: 3,
};

console.log(Object.prototype.hasOwnProperty.call(obj, "a")); // true
console.log(Object.prototype.hasOwnProperty.call(obj, "d")); // false
```

```js
// in operator
const obj = {
  a: 1,
  b: 2,
  c: 3,
};

console.log("a" in obj); // true
console.log("hasOwnProperty" in obj); // false
```

```js
// Lodash
const obj = {
  a: 1,
  b: 2,
  c: 3,
};
console.log(_.has(obj, "a")); // true
console.log(_.has(obj, "hasOwnProperty")); // false
```

---

### Print Ranges Natively in JavaScript

```js
Number.prototype [ Symbol. iterator] = function() {
  for(let i = 0; i <= this; i++) {
    yield i;
  }
};
[...]; // [ 0, 1, 2, 3 ]
```

---

### Check/validate if a Property Exists in an Object

```js
const car = {
  engine: "2JZ-GTE",
  doors: 2,
};

console.log("doors" in car); // Result: true
console.log("manufacturer" in car); // Result: false
// This returns whether the property exists or not, not the value of it
```

---

### Check property on Object

```js
// ❌ instead of 💩
const newObject = {
  'attribute_1': attributel,
  'attribute_2': attribute2,
};
if (condition1) {
  newObject['attribute_3'] = attribute3;
}


// better do ✅
const newObject = {
  'attribute_1': attributel,
  'attribute_2': attribute2,
  ...(conditioni ? {'attribute_3': attribute3} : {}),
};

// even better
const insertIf = (condition, object) => condition ? object : {};

const newObject {
  'attribute_1': attributel,
  'attribute 2': attribute2,
  ...insertif( conditioni, {
    attribute 3': attribute3
  }),
}
```

---

### Find Duplications with 3 arrays (line then up 0, 1, 2, and so on)

```js
const name = ["ball", "bat", "glove", "glove", "glove"];
const price = [2, 3, 1, 2, 1];
const weight = [2, 5, 1, 1, 1];

// make an AOO from 3 arrays
const arr = name.map((name, index) => {
  return {
    name: name,
    price: price[index],
    weight: weight[index],
  };
});

// check duplication
const uniqueArr = new Set(arr.map((v) => v.name && v.price && v.weight));

if (uniqueArr.size < arr.length) {
  console.log("duplicates found");
}
```

---

### shallowCompare

```js
shallowCompare = (obj1, obj2) =>
  Object.keys(obj1).length === Object.keys(obj2).length &&
  Object.keys(obj1).every((key) => obj1[key] === obj2[key]);

shallowCompare([1, 2], 1, 2); // true
```

---

### Get latest value form Array

```js
const formEvents = fromEvent(formField, "click");
const subscription = formEvents
  // 1st pipe
  .pipe(
    map(convertToAppropriateValue),
    // now the next request won't begin until the previous completes
    concatMap(saveRequest)
  )
  // 2nd susbcribe
  .subscribe();
```

---

### Difference/Complement between 2 arrays. Simetrical difference.

```js
// 1
var arr1 = [1, 2, 3];
var arr2 = [2, 3];

arr1.filter((x) => !arr2.includes(x)); // [1]
```

```js
// 2
const arrayOne = [
  { value: "1", display: "Leo" },
  { value: "2", display: "Carley" },
  { value: "3", display: "Tom" },
  { value: "4", display: "Sam" },
  { value: "5", display: "noName" },
];

const arrayTwo = [
  { value: "1", display: "Leo" },
  { value: "2", display: "Carley" },
  { value: "3", display: "Tom" },
  { value: "4", display: "Sam" },
];

results = arrayOne.filter(
  ({ value: id1 }) => !arrayTwo.some(({ value: id2 }) => id2 === id1)
);
// {value: "5", display: "noName"}
```

---

## contains white space

```js
const containsWhitespace = (str: string) => /\s/.test(str);

containsWhitespace("lorem"); // false
containsWhitespace("lorem ipsum"); // true
```

---

## for-of  and for-in

```js
const arr = [1, 2, 3, 4, 5];
// Long-hand
 for (let i = 0; i < arr.length; i++) {
   const element = arr[i];
 }

// Short-hand
 for (const element of arr) {
 }
 const obj =
  a: 1,
  b: 2,
   с: 3,
 };
```

```js
// Long-hand
 const keys S = Object. keys(obj);
 for (let i keys. length; i++) {
   const key = keys[i];
  const value = obj[key];
 }

 // Short-hand
 for (const key in obj) {
   const value = obj[key];
  //
 }
 ```

---

## Handling events comparison: `JS` Vs `RxJS`

So you can see the true power of RxJS now: The operators!!!!

```js
// ❌ instead of 💩
const button = document.querySelector("button");
const output = document.querySelector("output");

button.addEventListener("click", (e) => {
  output.textContent = Math.random().toString(36).slice(2);
});

// better do ✅
const output = document.querySelector("output");
const button = document.querySelector("button");

Rx.Observable.fromEvent(button, "click").subscribe(() => {
  output.textContent = Math.random().toString(36).slice(2);
});
```

** LINKS
https://codepen.io/mmiszy/pen/jGwzzG

---

## Remove an element from an array

```js
const removeElement = (arr, element) => arr.filter((e) => e !== element);

removeElement([1, 2, 3, 4], 2); // [1, 3, 4]
```

---

## Remove Duplicated from Array

```js
const removeDuplicated = (arr) => [...new Set(arr)];

removeDuplicated([1, 2, 3, 3, 4, 4, 5, 5, 6]); // [ 1, 2, 3, 4, 5, 6 ]
```

---
### Remove Duplicated from Array of Objects


```js
const numberArrays = [
  undefined, Infinity,
  null, -12,-false, -5,
  undefined, 89, 9, null,
  Infinity, 5, NaN];
const objArrays = 
  [{id:-1}, {id: 4}, {id: 1}, {id:-5}, {id: 4}];

console. log(
// [undefined, Infinity, 12, NaN, false, 5, 7, null, 89, 9]
Array. from(new Set(numberArrays)),
//[{id:-1}, {id:-4}, {id:-1}, {id:-5}, {id:-4}]
// nothing changes because even though the ids repeat in some objects
// the objects are different instances, different objects
Array.from(new Set(objArrays) )
)

const idSet = new Set();

console. log(
  // [{id: 1}, {id: 4}, {id: 5}] using id to track unique id
  objArrays.filter(obj => {
  const existingld = idSet.has(obj.id);
  idSet.add(obj.id);

  return !existingld;

  })
)
``` 

---

### Find largest numbers

```js
const findLargest = (arr) => arr.map((subArr) => Math.max(...subArr));
console.log(
  findLargest([
    [4, 5, 1, 3],
    [13, 27, 18, 26],
    [32, 35, 37, 39],
    [1000, 1001, 857, 1],
  ])
); // [5, 27, 39, 1001]
```


---

### Converts: to Observable: `of()`

```js
class Order<T> {
  constructor(
    public product: T,
    public address: string,
    public id: number,
  ) {}
}

of(
  new Order('name', 'address 1', 1),
  new Order('name 1', 'address 2', 2),
  new Order('name 2', 'address 3', 3),
).pipe(
  filter(order => order.id > 1),
  tap(order => doSomethingWithOrder(order))
).subscribe(order => {
  // do something with each order
});
```

---

### Converts: Integer -> Array of Digits

```js
Array.from(String(12345), Number); //  [1, 2, 3, 4, 5]
```

---

### Converts: a list of [key, value] pairs into an object

```js
const fromPairs = (pairs) =>
  pairs.reduce((a, b) => ({ ...a, [b[0]]: b[1] }), {});
  console.log(
      fromPairs([
      ["a", 1],
      ["b", 2],
      ["c", 3],
    ])
  ); // { a: 1, b: 2, c: 3 }
```

---

### handle events for rxjs. Subject is an Observer

Essentially this reads like this: take every mouse click, do a side effect, and then dump all of them into another stream.

```js
// ❌ instead of 💩
const clicks$ = fromEvent<MouseEvent>(document.body, 'click');
const allEvents$ = new Subject<Event>();

allEvents$.subscribe(event => doSomethingWithGlobalEvent(event));

clicks$.pipe(
  tap(event => performSomeSideffect(event)),
).subscribe(
  event => allEvents$.next(event),
  error => allEvents$.error(error),
  () => allEvents$.complete(),
);

// better do ✅
const clicks$ = fromEvent<MouseEvent>(document.body, 'click');
const allEvents$ = new Subject<Event>();

allEvents$.subscribe(event => doSomethingWithGlobalEvent(event));

clicks$.pipe(
  tap(event => performSomeSideffect(event)),
).subscribe(allEvents$);
```

---

### take first word and last from string ofword

```js
//.startsWith:
const str = "Hello World!";

console.log(str.startsWith("Hello")); // True
```

```js
const totn_string = "TechOnTheNet";

console.log(totn_string.startsWith("Tech")); // true
console.log(totn_string.startsWith("TECH")); // false
```

```js
const totn_string = "TechOnTheNet";

console.log(totn_string.startsWith("On", 4)); // true
```

```js
// .endsWith()
const str = "Hello World!";

console.log(str.endsWith("Hello")); // False
```

```js
// .includes()
const str = "Hello World!";

console.log(str.includes(" ")); // True
console.log("JS ".repeat(3)); // JS JS JS
```

```js
// .some()
function isBiggerThan10(element, index, array) {
  return element > 10;
}

[2, 5, 8, 1, 4].some(isBiggerThan10); // false
[12, 5, 8, 1, 4].some(isBiggerThan10); // true
```

```js
// .every()
function isBigEnough(element, index, array) {
  return element >= 10;
}
[12, 5, 8, 130, 44].every(isBigEnough); // false
[12, 54, 18, 130, 44].every(isBigEnough); // true
```

```js
// .substr()
// The substr() method does not change the value of the original string
var totn_string = "TechOnTheNet";

console.log(totn_string.substr(0, 4)); // Tech
console.log(totn_string.substr(4, 2)); // On
console.log(totn_string.substr(6, 3)); // The
console.log(totn_string.substr(9, 3)); // Net
console.log(totn_string.substr(-3)); // Net
```

```js
// .substring()
// The substring() method does not change the value of the original string
var totn_string = "TechOnTheNet";

console.log(totn_string.substring(0, 4)); // Tech
console.log(totn_string.substring(4, 6)); // On
console.log(totn_string.substring(6, 9)); // The
console.log(totn_string.substring(9, 12)); // Net
```

---

### Different ways of writing the same function

```js
// same
function foo(user) {
  return { password: user.password };
}

// same
const foo = (user) => {
  // A function defined with => doesn't have a this to reference.
  return { password: user.password };
};


// same
const foo = (user) => {
  // A function defined with => doesn't have a this to reference.
  const password = user.password;
  return { password: password };
};

// same
const foor = (user) => {
  // A function defined with => doesn't have a this to reference.
  const password = user.password;
  return { password };
};

// same
const foo = ({ password }) => {
  // A function defined with => doesn't have a this to reference.
  return { password };
};

// same
const foo = ({ password }) => ({
  // A function defined with => doesn't have a this to reference.
  password,
});
```

---

### Comparing Arrays

```js
const isArraysEqual = (arr1, arr2) => arr1.length === arr2.length 
  && arr1.every((ele1, index1) => ele1 === arr2[index1]);

console.log(isArraysEqual([2,3,7,10], [2,3,7,10])); // true

console.log(isArraysEqual([2,3,7,10], [2,3,7,10,11])); // true
```

---

### Logical OR assignment: `expr1 ||= expr2`. Logical operator

The logical OR assignment `(x ||= y)` operator only assigns if x is falsy.

```js
const a = { duration: 50, title: "" };

a.duration ||= 10;
console.log(a.duration); // 50

a.title ||= "title is empty.";
console.log(a.title); // "title is empty"
```

---

### Double Bitwise: `~~` Logical operator

> use ~~ instead of Math.floor()

The double NOT bitwise operator approach only works for 32 bit integers i.e:

```js
// ❌ instead of 💩
Math.floor(5.9) === 4; // true

// better do
~~5.9 === 4; // true
```

```js
~~null; // 0
~~undefined; // 0
~~0; // 0
~~{}; // 0
~~[]; // 0
~~{ 1: 1 }; // 0
~~(1 / 0); // 0
~~false; // 0
~~true; // 1
~~1.2543; // 1
~~4.9; // 4
~~-2.999; // -2
```

---

### Bitwise NOT: `~` Logical operator

the ~ operator will truncate any fractional component of an input Number

```js
var someText = "javascript rules";

!!~someText.indexOf("tex"); // false
~someText.indexOf("asd"); // someText doesn't contain "asd" - false
~someText.indexOf("ext"); // someText contains "ext" - true

~2; //returns -3
~"2"; //returns -3
~"-3" - // returns 2
  "-3.14"; // returns 2
~"-3.54"; // returns 2
~"0xFF"; // returns -256
~true; // returns -2
~"123e-5"; // returns -1
~false; // returns -1
~null; // returns -1
~"Infinity"; // returns -1
~"infinity"; // returns -1
~function (val) {
  return val;
}; // returns -1
~{
  valueOf: function () {
    return "0xFF";
  },
};
```

> The gotcha is the bitwise operator ~, "Bitwise operators perform their operations on binary representativesntations, but they return standard JavaScript numerical values."

> It transforms -1 into 0, and 0 evaluates to false in JavaScript.

---

### Bitwise NOT: `~~foo` Logical operator

The double bitwise NOT is not actually an operator on its own, it's just applying the single bitwise NOT operator (~) twice.

```js
~~null; // 0
~~undefined; // 0
~~0; // 0
~~{}; // 0
~~[]; // 0
~~(1 / 0); // 0
~~false; // 0
~~true; // 1
~~1.2543; // 1
~~4.9; // 4
~~5.7; // 5
~~-2.999; // -2
```

```js
// ❌ instead of 💩
/*Array.prototype.indexOf = function...*/
var from = Number(arguments[1]) || 0;
from = from < 0 ? Math.ceil(from) : Math.floor(from);

// better do ✅
/*Array.prototype.indexOf = function...*/
var from = ~~arguments[1];
```

---

### Bitwise XOR: `(^)` Logical operator

The ^ operator performs an XOR (exclusive-OR) operation on each pair of corresponding bits of its operands. The ^ operator returns 0 if both bits are the same (either 0 or 1); otherwise, it returns 1.

```js
((((0 ^ 0) === 0(0 ^ 1)) === 1(1 ^ 0)) === 1(1 ^ 1)) === 0;

const A = 1;
A ^ 0; // A
A ^ ~A; // -1
A ^ A; // 0
A ^ -1; // ~A
```

---

### indexOf() with `!!~` Logical operator

> It transforms -1 into 0, and 0 evaluates to false in JavaScript.

```js
// ❌ instead of 💩
if (arr.indexOf(item) > -1) {
  // item found
}
if (arr.indexOf(item) === -1) {
  // item not found
}
// better do ✅
if (~arr.indexOf(item)) {
  // item found
}
if (!~arr.indexOf(item)) {
  // item not found
}
```

```js
// Logical NOT (!)
// The following would return true in case myArray is empty, that is [], or undefined or null.
const myArray = [];
!myArray?.length ? true : false; // true

const myArray = {};
!myArray?.length ? true : false; // true

const myArray = undefined;
!myArray?.length ? true : false; // true

const myArray = [1,2,3];
!myArray?.length ? true : false; // false
```

```js
var someText = "javascript rules";
console.log(someText.indexOf(true)); // -1

~someText.indexOf("xxxex"); // 0
!!~someText.indexOf("xxxex"); // false

~someText.indexOf("asd"); // 0
!!~someText.indexOf("asd"); // false

~someText.indexOf("rule"); // -12
!!~someText.indexOf("rule"); // true
```

The gotcha is the bitwise operator `~`, Bitwise operators perform their operations on binary representations, but they return standard JavaScript numerical values.`

```js
// Even better:
"something".includes("thing"); // true
["leo", "JS"].includes("leo"); // true
[(1, 2, 3)].includes(1); // true
```

---

### Wait until multiple promises are complete

As each task is ran asynchronously, they can be processed in parallel and the returned data can be used once all promises are resolved.

Bear in mind that if a single promise is rejected, Promise.all will also return a rejected promise immediately.

```js
const promises = [
  Promise.resolve(100),
  fetch("https://jsonplaceholder.typicode.com/posts"),
  fetch("https://jsonplaceholder.typicode.com/posts/1/comments"),
];

const statusPromises = await Promis.all(promises);
console.log(statusPromises); // 0: 100, 1: Request response, 2: Request response
console.log("ALL Promises finished execution");
```

---

### ‘Promise.any()'

Promise.any() is a new feature that takes several iterable promises and returns the promise that is fulfilled first. An example will make that clear for you:

```js
const p1 = new Promise((resolve) => setTimeout(resolve, 500, "First"));
const p2 = new Promise((resolve) => setTimeout(resolve, 800, "Second"));
const p3 = Promsie.reject(1);
const promises = [p1, p2, p3];

Promise.any(promises)
  .then((result) => {
    console.log(result);
  }) // the result would be 'First' because that's the promise, that is fulfilled first.
  .catch((e) => {
    console.log(e);
  });
```

---

### Promise.allSettled()

allSettled() takes an array of promises as an argument. It returns a new promise in the form of an array containing all the statuses for each promise we passed to it.

```js
const promise1 = new Promise((resolve, reject) => {
  resolve("The Promise number 1 was resolved");
});
const promise2 = new Promise((resolve, reject) => {
  reject("The Promise number 2 was rejected");
});
const promise3 = new Promise((resolve, reject) => {
  resolve("The Promise number 3 was resolved");
});

// Using allSettled().
Promise.allSettled([promise1, promise2, promise3])
  .then((result) => console.log(result))
  .catch((err) => console.log(err))[
];
  // ({ status: "fulfilled", value: "The Promise number 1 was resolved" },
  // { status: "rejected", reason: "The Promise number 2 was rejected" },
  // { status: "fulfilled", value: "The Promise number 3 was resolved" })
```

---

### Promise.any and AggregateError

```js
Promise.any([
  fetch("https://v8.dev/").then(() => "home"),
  fetch("https://v8.dev/blog").then(() => "blog"),
  fetch("https://v8.dev/docs").then(() => "docs"),
])
  .then((first) => {
    // Any of the promises was fulfilled.
    console.log(first);
    // → 'home'
  })
  .catch((error) => {
    // All of the promises were rejected.
    console.log(error);
  });

// ^ In the above example error is an AggregateError
```
---

### Swap two variables no memory used

```js
// ❌ instead of 💩
let numOne = 1,
  numTwo = 2;

const temp = numOne;
numOne = numTwo;
numTwo = temp;

console.log(numOne, numTwo); // 2 1

// better do ✅
let numOne = 1,
  numTwo = 2;
[numOne, numTwo] = [numTwo, numOne];

console.log(numOne, numTwo); // 2 1
```

---

### Assign values to multiple variable

```js
// ❌ instead of 💩
let numOne = 1;
let numTwo = 2;
let numThree = 2;

// better do ✅
let [numOne, numTwo, numThree] = [1, 2, 3];
```

---

### Creates a new function that adds a delay in milliseconds to the execution of another function that is passed as an argument.

```js
function addDelay(func: () => void, ms: number) {
  return () => {
    setTimeout(() => {
      func();
    }, ms);
  };
}

function sayHello() {
  console.log("Hello world!");
}

const delayedSayHello = addDelay(sayHello, 600);
delayedSayHello(); // Prints "Hello world!" (after 600 ms)
```

---

### Memoization

- Functions that are expensive to run can be optimised with memoisation.
- This involves using a closure to cache the results of previous calls to the function
- Memoization should be mainly used to speed up slow-performing, costly or time-consuming function calls
- Memoization speeds up subsequent calls, so it is best used when you anticipate multiple calls of the same function under the same circumstances
- Memoization stores results in memory, therefore it should be avoided when the same function is called multiple times under very different circumstances

```js
var memoise = function (func) {
  var cache = {};
  return function (arg) {
    if (arg in cache) {
      console.log(arg + " in cache");
      return cache[arg];
    } else {
      console.log(arg + "not in cache");
      return (cache[arg] = func(arg));
    }
  };
};

var memo = memoise(function (n) {
  return n * 2;
});

console.time("not in cache");
memo(1); // 2 (1 not in cache)
console.timeEnd("not in cache");
console.time("cache");
memo(1); // 2 (1 in cache)
console.timeEnd("cache");
```

```js
const object = { a: 1, b: 2 };
const other = { c: 3, d: 4 };

const values = _.memoize(_.values);
values(object); // => [1, 2]

values(other); // => [3, 4]

object.a = 2;
values(object); // => [1, 2]

// Modify the result cache.
values.cache.set(object, ["a", "b"]);
values(object); // => ['a', 'b']

_.memoize.Cache = WeakMap; // Replace `_.memoize.Cache`.
```

```js
const memoize = (fn) => {
  const cache = new Map();
  const cached = function (val) {
    return cache.has(val)
      ? cache.get(val)
      : cache.set(val, fn.call(this, val)) && cache.get(val);
  };
  cached.cache = cache;
  return cached;
};

// See the `anagrams` snippet.
const anagramsCached = memoize(anagrams);
anagramsCached("javascript"); // takes a long time
anagramsCached("javascript"); // returns virtually instantly since it's cached

console.log(anagramsCached.cache); // The cached anagrams map
```

```js
// ej4
const memoize = (fn) =>
  new Proxy(fn, {
    cache: new Map(),
    apply(target, thisArg, argsList) {
      let cacheKey = argsList.toString();
      if (!this.cache.has(cacheKey))
        this.cache.set(cacheKey, target.apply(thisArg, argsList));
      return this.cache.get(cacheKey);
    },
  });

const fibonacci = (n) => (n <= 1 ? 1 : fibonacci(n - 1) + fibonacci(n - 2));
const memoizedFibonacci = memoize(fibonacci);

for (let i = 0; i < 100; i++) fibonacci(30); // ~5000ms
for (let i = 0; i < 100; i++) memoizedFibonacci(30); // ~50ms
```

```js
// OBSCRURE Fibonacci
const fib = function (_) {
  for (
    _ = [+[], ++[[]][+[]], +[], _],
      _[++[++[++[[]][+[]]][+[]]][+[]]] =
        ((_[++[++[++[[]][+[]]][+[]]][+[]]] - ++[[]][+[]]) &
          (--[[]][+[]] >>> ++[[]][+[]])) ===
        _[++[++[++[[]][+[]]][+[]]][+[]]] - ++[[]][+[]]
          ? ((_[++[++[[]][+[]]][+[]]] = ++[[]][+[]]),
            _[++[++[++[[]][+[]]][+[]]][+[]]] - ++[[]][+[]])
          : +[];
    _[++[++[++[[]][+[]]][+[]]][+[]]]--;
    _[+[]] =
      (_[++[[]][+[]]] = _[++[++[[]][+[]]][+[]]] = _[+[]] + _[++[[]][+[]]]) -
      _[+[]]
  );
  return _[++[++[[]][+[]]][+[]]];
};

fib(6); // 8
```

---


### `readonly` and `as const` make that property immutable.

```js
interface MyInterface {
  readonly myProperty: string
}
let foo: MyInterface = {
  myProperty: 'hi'
}

foo.myProperty = "bye" // compiler err, saying myProperty is Read Only
```

```js
let t = {
  myProperty: "hi"
  myArr: [1, 2, 3]
} as const;
```

---

### `??` impossible for undefined to be passed into the function.

This is because the null coalescence operator makes it so that if what is on the left-hand side is undefined, we instead pass in what's on the right, an empty string.

```js
sendFieldToServer(textField?.text ?? "");
```

---

### `!` and `!!` non-null assertion operator. MB

```js
// = xxx!.nnn;
// Compiled with --strictNullChecks
function validateEntity(e?: Entity) {
  // Throw exception if e is null or invalid entity
}
function processEntity(e?: Entity) {
  validateEntity(e);
  let s = e!.name; // Assert that e is non-null and access name
}
```

```js
// = nnn!!;
const validation = (product?: IProduct) => {
    // Este fragmento podría lanzar una excepción en caso de no ser válida
}

const checkUrl = (product?: IProduct) => {
   validation(product);
   const assertedProduct = product!!;
   // a partir de aquí podemos usar el objeto assertedProduct que asegura no ser nulo
   const url = assertedProduct.url;
}
```

---

### Functions in TS Interfaces

```js
interface IMyAwesomeInterface {
  sum: (a: number, b: number) => number;
}
```



---

### Accessing object properties (and methods) by [bracket] notation

```js
let someObject = {
  cat: "meow",
  dog: "woof",
  duck: "quack",
};
console.log(someObject.cat); // meow
console.log(someObject["cat"]); // meow
```

```js
let someObject = {
  cat: "meow",
  dog: "woof",
  duck: "quack",
};

let props = Object.keys(someObject);
console.log(props); // ['cat', 'dog', 'duck']
```

---

### Get an Objects Keys and Values

```js
const obj = { 
  name: "Daniel", age: 40, occupation: "Engineer", level: 4 
};

// Getting an object's keys
console.log(Object.keys(obj)); // ["name", "age", "occupation", "level"]

// Getting an object's values
console.log(Object.values(obj)); // ["Daniel", 40, "Engineer", 4]

// Getting an object's entries
console.log(Object.entries(obj)); // [["name", "Daniel"], ["age", 40], ["occupation", "Engineer"], ["level", 4]]

// Reform an object
const objEntries = Object.entries(obj);
console.log(Object.fromEntries(objEntries)); // {name: "Daniel", age: 40, occupation: "Engineer", level: 4}
```

```js
// for in loop
const myPropNames = [];

for (let prop in obj) {
  myPropNames.push(prop);
}

console.log(myPropNames); // ['name', 'age', 'occupation', 'level']
```

```js
// getOwnPropertyDescriptors
const myCarDescriptors = Object.getOwnPropertyDescriptors(myCar );

console. log(myCarDescriptors);
// {name: {..}, age: {..}, occupation: {..}, drlevelive: {..}..}
```

```js
// Reflect.ownKeys
// obtain keys/names of all own, including non enumerable and symbolic, properties of a given object aggregated in an array
const myCarOwnKeys = Reflect.ownKeys(obj);

console.log(myCarOwnKeys); // ['name', 'age', 'occupation', 'level'] 
```

---

### Numeric separators

The value is unchanged, it is simply easier to read.

```js
let duration = 10_000_000;

console.log(duration); // 10000
console.log(duration * 2); // 20000
```

---

### Extracting items from an array

```js
const a = [1, 2, 3, 4, 5];
const [valueAtPosition1, valueAtPosition2] = a;

console.log(valueAtPosition1, valueAtPosition2); // 1, 2
```

---

### `setter/getter` or `mutators/accessors`

```js
Mutator Method (Setter):
To mutate a value, we use a set method.

Accessor Method (Getter):
To access a value, we use a get method.
```

Accessor and Mutator methods encapsulate our classes, keeping them safe by hiding unnecessary implementation details and only modifying certain values.

Use TypeScript getters/setters to control the access properties of a class.

Where we do the reading(get) and writing(get) majorly determines how much cost we pay for performance.

Now the catch with this is, every time Angular performs change detection, the getters get called.

Getters have a negative effect on change detection. In order to know whether the view should be updated, Angular needs to access the new value, compare it with the old one and make the decision on whether the view should be updated. For this reason, the value is compared and updated on every change detection cycle. This can cause performance issues and circumvents certain configurations like OnPush.

```js
A setter function is called every time we write some value. getters A
getter function is called every time we read some value.
```

---

### add if else condition in the Observable

```js
this.data$.pipe(
  switchMap(() => {
    if (canDeactivate) {
      return Observable.of(canDeactivate);
    } else {
      return Observable.of(window.confirm("test"));
    }
  })
);
```

---


### Check whether an optional parameter was provided

```js
function checkSomething(a, b?) {
  if (b == null) callMethod();
}
```

---

### Build a custom Type Guard

```js
interface IBird{
  name: string;
  feathersColor: string;
}

interface IFish{
  name: string;
  finsColor: string;
}

type Animal = IBird | IFish;

/** Custom Type Guard */
const isBird = (animal: Animal): animal is IBird => {
  let res_ = (animal as IBird).feathersColor !== undefined;
  return res_;
}

const parrot: Animal = {name: "Parrot", feathersColor: "green"};
const oscar: Animal = {name: "Oscar", finsColor: "orange"};

console.log(isBird(parrot)); //first call with a bird
console.log(isBird(oscar)); //second call with a fish
```

---

### Nested object deep object validation: Parameter Guard. ES2021`.?`

> Optional Chaining Operator: This operator enables to return undefined or fallback value if any reference is nullish values - null or undefined.

```js
// ej0
// ❌ instead of 💩
let str = ''
let finalStr

if (str !== null && str !== undefined) {
  finalStr = 'default string'
} else {
  finalStr = str
}

// better do
let str = '';
let finaStr = str ?? 'default string'; // ''
```






```js
// ej1
// ❌ instead of 💩
const test = (master: IMaster) => {
  if (
    master &&
    master.detail &&
    master.detail.deepDetail &&
    master.detail.deepDetail.foo
  ) {
    // ...
  }
};

// better do ✅
// ES11: Optional Chaining Operator
const test = (master: IMaster) => {
  if (master?.detail?.deepDetail?.foo) {
    // ...
  }
};
```

```js
// ej2
// ❌ instead of 💩
get isAdyenError(): boolean {
    if (this.status && && this.status.errorData && this.status.errorData.error_type === 'ADYEN_PAYMENT') {
        return true;
    }
    return false;
}

// better do ✅
get isAdyenError(): boolean {
  // this is valid on TS
  return this.status?.errorData?.error_type === 'ADYEN_PAYMENT';
}
```

```js
// insterad of
let num = null
let actualNum

if (num !== null && num !== undefined) {
  actualNum = num
} else {
  actualNum = 0
}

// better do ✅
let num = null
let actualNum = num ?? 0 // 0
```

---

### Implicit Return Shorthand

```js
/// instead f
function calcCircumference(diameter) {
  return Math.PI * diameter;
}

// better do ✅
calcCircumference = (diameter) => Math.PI * diameter;
```

```js
var simple = (a) => (a > 15 ? 15 : a);

simple(16); // 15
simple(10); // 10
```

```js
let max = (a, b) => (a > b ? a : b);

max(2, 3); // 3
```

---

### Object Property declaration shorthand.

```js
// ❌ instead of 💩
const x = 1920;
const y = 1080;

const obj = { x: x, y: y };

// better do ✅
const x = 1920,
  y = 1080;

const obj = { x, y };
x; // 1920
y; // 1080
```

---

### Multi-line String Shorthand

```js
// ❌ instead of 💩
const lorem =
  "Lorem ipsum dolor sit amet, consectetur\n\t" +
  "adipisicing elit, sed do eiusmod tempor incididunt\n\t" +
  "ut labore et dolore magna aliqua. Ut enim ad minim\n\t" +
  "veniam, quis nostrud exercitation ullamco laboris\n\t" +
  "nisi ut aliquip ex ea commodo consequat. Duis aute\n\t" +
  "irure dolor in reprehenderit in voluptate velit esse.\n\t";

// better do ✅
const lorem = `Lorem ipsum dolor sit amet, consectetur
    adipisicing elit, sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua. Ut enim ad minim
    veniam, quis nostrud exercitation ullamco laboris
    nisi ut aliquip ex ea commodo consequat. Duis aute
    irure dolor in reprehenderit in voluptate velit esse.`;
```

---

### Generating a random number within a range

```js
const randomNumberInRange = (min, max) =>
  Math.floor(Math.random() * (max - min + 1)) + min;

randomNumberInRange(1, 100); // 22
```

---

### Create random sort order

```js
const sortRandom = (arr) => arr.sort(() => Math.random() - 0.5);

sortRandom([1, 2, 3, 4, 5]); // [4, 3, 1, 5, 2]
```

---

## array sort

```js
const arr = [1, 2, 20, 10, 8];

arr.sort(); // [1, 10, 2, 20, 8]
arr.sort((a, b) => a - b); // [1, 2, 8, 10, 20]
```

---


### Delay function. Utility

```js
// Code
const delay = (fn: Function, wait: number, ...args: any[]) =>
  setTimeout(fn, wait, ...args);

// How to use it
delay(
  function (text) {
    console.log(text);
  },
  1000,
  "later"
); // Logs 'later' after one second.
```

---

### Delay Promise. Utility

```js
const delayedPromise = (wait: number = 2000, ...args: any[]) =>
  new Promise((resolve) => {
    console.log('Delay started:', new Date()); // Log start of simulated delay
    setTimeout(resolve, wait, ...args);
});

(async function () {
  await delayedPromise();
  console.log("Print after delay");
})(); // Print after delay
```

---

### Checking whether all items in an array meet a certain condition

```js
const isOldEnough = (age) => age >= 18;
const ages = [7, 19, 12, 33, 15, 49];
ages.every(isOldEnough); // Results in false
const olderPeople = [39, 51, 33, 65, 49];

olderPeople.every(isOldEnough); // true
```

---

### Calculate the number of days between two dates

```js
const daysBetweenDates = (dateA, dateB) => {
  const timeDifference = Math.abs(dateA.getTime() - dateB.getTime());

  // Seconds * hours * miliseconds
  return Math.floor(timeDifference / (3600 * 24 * 1000));
};
daysBetweenDates(new Date("2020/10/21"), new Date("2020/10/29")); // 8
daysBetweenDates(new Date("2020/10/21"), new Date("2021/10/29")); // 373
```

---

### Extract hostname from URL

```js
const extractHostname = (url) => {
  let hostname = url.indexOf("//") > -1 ? url.split("/")[2] : url.split("/")[0];
  // Remove port number.
  hostname = hostname.split(":")[0];
  // Remove querystring.
  hostname = hostname.split("?")[0];
  return hostname;
};

extractHostname("https://www.leolanese.com"); // "www.leolanese.com"
```

---

### Capitalise a string

```js
const capitalize = (str) => str.charAt(0).toUpperCase() + str.slice(1);

capitalize("hello world"); // "Hello world"
```

### capitalize ALL words in string

```js
function toTitleCase(str) { 
  return str.replace(/\b\w/g, l => l.toUpperCase());
} 

toTitleCase("hello world from javascript"); // 'Hello World From Javascript'

\b: Matches a word boundary (position before the first letter of each word).
\w: Matches the first word character following the word boundary.
g: Ensures the pattern is applied globally, throughout the entire string.
```

---

### Toggling a boolean

```js
const toggle = (value) => (value = !value);

toggle(false); // true
toggle(true); // false
```

---

### Sort Ascending / Descending

```js
// sort ascending
const numbers = [40, 100, 1, 5, 25, 10];
const sortedNumbers = [...new Float64Array(numbers).sort()];

sortedNumbers; // [1, 5, 10, 25, 40, 100]
```

```js
// sorting descending = `.reverse()`
const numbers = [40, 100, 1, 5, 25, 10];
numbers.sort((a, b) => b - a;);

console.log(numbers); // [100, 40, 25, 10, 5, 1]

// or simply just .reverse()
const sortedNumbers = [...new Float64Array(numbers).sort()];

sortedNumbers.reverse(); // [100, 40, 25, 10, 5, 1]
```

---

### Repeat a string for multiple times

```js
// Longhand
let str = "";
for (let i = 0; i < 5; i++) {
  str += "Hello ";
}
console.log(str); // Hello Hello Hello Hello Hello

// Shorthand
"Hello".repeat(5);
```

---

### Exponent Power

```js
// Longhand
const power = Math.pow(4, 3); // 64

// Shorthand
const power = 4 ** 3; // 64
```

---

### export & import

#### export: Two ways to export

1. `Exporting at the moment of declaration`. Putting the `export` statement on the same line right before the variable, function or class you are about to declare.

```js
// Declare and export variables
export const MY_PASS = "Some very important secret.";
export let name = "Jack";
export var stack = "JS";

// Declare and export functions
export function sayHi() {
  return "Hi.";
}

export const sayBye = function () {
  return "Bye.";
};

export const sayGoodBye = () => {
  return "Good bye.";
};

// Declare and export class
export class Person {
  name = this.name;
  age = this.age;
  #my_secret = this.secret;
}
```

2. `Declaring it first and exporting it after that`. In this case, you use the export statement followed by the "thing" you want to export.

```js
// Declare some stuff
const MY_PASS = "Some very important secret.";

let name = "Jack";

function sayHi() {
  return "Hi.";
}

class Car {
  numOfWheels = this.numOfWheels;
  typeOfFuel = this.typeOfFuel;
}

// Export all the stuff at once
export { MY_PASS, sayHi, Car };
```

##### export: Named and default export

```js
// Named export
export const LANG = 'Spanish'

// or
const favoriteFantasy = 'LORD'
export favoriteFantasy


// Default export
export default const LANG = 'Spanish'

// or
const favoriteFantasy = 'LORD'
export default favoriteFantasy

// Another way to create default export using {}
const FAVORITE_SEASON = 'Sprint'

// Export FAVORITE_SEASON as default
export { FAVORITE_SEASON as default }
```

#### import rules

##### with or without {}

When importing named exports, you have to wrap those names with curly braces. This is required when you import named exports.

```js
import { someModule } from "file.js";
import someModule from "file.js";
```

##### Default imports

If you exported some module as default, you can choose whatever name to import that module you want. And, don't wrap the module name with curly braces if you want to import default export.
Also when import something as default, you don't use the variable keyword.

```js
// File 1: file-one.js
// Declare and export some stuff as default
// Note: omit the "const", "let" or "var" keywords
export default surname = "Joe";

// File 2: file-two.js
// Import only default export "name"
// Note: no curly braces around the name
import surname from "./file-one.js";

// Try to read imported "age" variable
console.log(surname); // Joe
```

```js
// File 1: file-one.js
// Declare and export some variable as default
export default secret = "This is some very important secret.";

// File 2: file-two.js
// Import the default export using a different name
import password from "./file-one.js";

// Try to read imported "age" variable
console.log(password); // This is some very important secret.
```

- LINKS
  https://dev.to/alexdevero/import-and-export-statements-in-javascript-and-how-to-use-them-1cnm?utm_source=digest_mailer&utm_medium=email&utm_campaign=digest_email

---

### Elvis Operator. Nested deep object validation

```js
// ❌ instead of 💩
const street;
if (user && user.address && user.address.street) {
 street = user.address.street;
}

// better do ✅
const street = user?.street?.address;
```

```js
// ❌ instead of 💩
if (typeof person !== "undefined" && person !== null) {
  person.greet();
}

// better do ✅
if (!!person) {
  person.greet();
}
```

```js
// ❌ instead of 💩
name: this.model && this.model.data ? this.model.data.name : undefined,

// better do ✅
this.model?.data?.name || undefined,
```

---

### function constructor

```js
// ES5
function Person(name) {
  this.name = name;
}
Person.prototype.describe = function () {
  return "Person called " + this.name;
};
```

```js
// ES6
class Person {
  constructor(name) {
    this.name = name;
  }
  describe() {
    return "Person called " + this.name;
  }
}
```

---

### Join & shollow clone arrays using spread operators

```js
// instead of
const oddNumbers = [3,5,7]
const numbers = [2,4,6].concat(oddNumbers);

// better do
const numbers = [2,4,6,...oddNumbers];
const array = [1,2,3];
const arrayClone = [...array];
```

```js
// instead of
// not Object.assign()
const arr = [1, 2, 3]
const biggerArr = [4,5,6].concat(arr)
const smallObj = {x: 1}
const otherObj = object.assign(smallObj, {y: 2})

// better do
// Use array destructuring to concatenate arrays
const arr = [1, 2, 3]
const biggerArr = [4, 5, 6, ...arr]
// Use object spread syntax to create a new object with properties of the original object
const smallObj = {x: 1}
const otherObj = {...smallObj, y: 2}
```

---

---

### Clone (immutable trick). Make a copy of an array

```js
const arr = [0, 1, 2];

const arrClone = [...arr]; // [0, 1, 2]
```

---


## spread operator in a function call

```js
function returnArgArray(...args) { 
  return args;
}

returnArgArray(...['x', 'y', 'z']); // [ 'x', 'y', 'z' ]
returnArgArray([...['a', 'b'], 'c']); // [ 'a', 'b', 'c' ]
returnArgArray({...{ a:1, b:2 }, c:3}); // [{a: 1, b: 2, c: 3}]
```

---

### `Object.assign` vs `Object Spread`

> '...' could be used to represent either a spread operator or a rest parameter

#### There's an easy way to distinguish between them:

- When `...` is at the end of function parameters, it's "rest parameters" and gathers the rest of the list of arguments into an array.

- When `...` occurs in a function call or alike, it's called a "spread operator" and expands an array into a list.

> The rest parameters must be at the end


### Spread:

The fundamental idea of the object spread operator is to create a new plain object using the own properties of an existing object.

> So {...obj} creates a new object with the same properties and values as obj

```js
const obj = { foo: "bar" };
const clone = { ...obj }; // { foo: 'bar' }
obj.foo = "baz";
clone.foo; // 'bar'
```

```js
// Object.assign()
let c = { a: 1 };
let d = Object.assign(c);
```

```js
// ❌ instead of 💩
return getAddedIds(state.cart).map((id) =>
  Object.assign({}, getProduct(state.products, id), {
    quantity: getQuantity(state.cart, id),
  })
);

// Better do ✅
return getAddedIds(state.cart).map((id) => ({
  ...getProduct(state.products, id),
  quantity: getQuantity(state.cart, id),
}));
```

- LINKS:
  Using Using Object Spread Operator instead Object.assign()
  https://redux.js.org/recipes/using-object-spread-operator

---

### use `...spread` or `.concat` instead a `.push`

```js
// ❌ instead of 💩
const arr1 ='['a'' 'b'' 'c'];
const arr2 ='['d'' 'e'' 'f'];
const arr3 = arr1.push(arr2);

console.log(arr3); // 4
console.log(arr1); //"["a"" "b"" "c","["d"" "e"" "f"]]


// better do ✅
const arr1 ='['a'' 'b'' 'c'];
const arr2 ='['d'' 'e'' 'f'];
const arr3 = arr1.concat(arr2);

console.log(arr3); /"["a"" "b"" "c"" "d"" "e"" "f"
```

```js
// even better
const arr1 = ['a', 'b', 'c'];
const arr2 = ['d', 'e', 'f'];
const arr3 = arr1.[...arr2];

console.log(arr3); //["a", "b", "c", "d", "e", "f"]]
```

---

### Object.assign()

```js
// ❌ instead of 💩
options = Object.assign({}, optionsDefault, options);

const x1 = (x) => Object.assign({}, x, { val: x.val + 1 });

// better do ✅ 
// Object spread
options = { ...optionsDefault, ...options };

const x1 = (x = { x, ...{ val: x.val + 1 } });
```

---

### Update Immutable object using pread operator

```js
const book = {
  name: "JavaScript: SOmethign smells here",
  author: "Leo Lanese",
  edition: 1,
  year: 2024,
};

const newerBook = {
  ...book,
  edition: 6, // Overwrites book.edition
  year: 2012, //  Overwrites book.year
};

console.log(newerBook); // {name: 'JavaScript: SOmethign smells here', author: 'Leo Lanese', edition: 6, year: 2012}
```

---

## DTO and TS Interfaces generator: `json -> ts` & `json -> Interface`

### Create Interfaces from API response

If you have a big, nested response from the API, 't's really tedious to type the corresponding interface(s) by hand.

### LINKS
https://transform.now.sh/json-to-go/<br>
https://app.quicktype.io/<br>
http://www.jsontots.com/ <br>
http://www.json2ts.com/<br>

---

## pluck / arrancar

```js
const pluck = (objs, key) => objs.map((obj) => obj[key]);


const users = [{ name: "Leo", age: 45 }, { name: "Tom", age: 7 }];

pluck(users, 'name'); // ['Leo', 'Tom']
```

---

### filter object with rxjs pluck

```js
import { from, of } from "rxjs";
import { pluck } from "rxjs/operators";

const source = of({
  name: "Joe",
  age: 30,
});
//grab names
const example = source.pipe(pluck("name")); // "Joe", "Sarah"
const subscribe = example.subscribe((val) => console.log(val));
```

LINKS<br>
https://stackblitz.com/edit/typescript-b68qdv?file=index.ts

---

### Use factory functions

> `Factory functions` are a type of function in JavaScript that are used to create and return new objects. They are called "factory" functions because they create and return new instances of an object, much like a factory creates and returns new products.


```js
function createFrog(name) {
  const children = [];

  return {
    addChild(frog) {
      children.push(frog);
    },
  };
}

const mikeTheFrog = createFrog("mike");
```

```js
function createPerson(name, age) {
  return {
    name: name,
    age: age,
    sayHello: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
}

// Create a new person object using the factory function
const person1 = createPerson('John', 30);
person1.sayHello(); 
```

---

### Dynamic Declaration Of Properties On Objects

```js
// eg1
const dynamic = 'color';
var item = {
    brand: 'Ford',
    [dynamic]: 'Blue'
}
console.log(item); // { brand: "Ford", color: "Blue" }
```

```js
// eg2
let dynamic = 'value';
let user = {
  id: 1;
}
user[dynamic] = 'new value';
user; // {id: 1, value: "new value"}
```

---

### trimStart() and trimEnd()

```js
const str = "   string   ";

// es2019
console.log(str.trimStart()); // "string   "
console.log(str.trimEnd()); // "   string"

// the same as
console.log(str.trimLeft()); // "string   "
console.log(str.trimRight()); // "   string"
```

---

### flat() and flatMap()

// flat() method enables you to easily concatenate all sub-array elements of an array

```js
const arr = ["a", "b", ["c", "d"]];

const flattened = arr.flat();
console.log(flattened); // ["a", "b", "c", "d"]
```

```js
const arr = ["a", , , "b", ["c", "d"]];

const flattened = arr.flat();
console.log(flattened); // ["a", "b", "c", "d"]
```

```js
const arr = [4.25, 19.99, 25.5];

console.log(arr.map((value) => [Math.round(value)])); // [[4], [20], [26]]
console.log(arr.flatMap((value) => [Math.round(value)])); // [4, 20, 26]
```

---

### Array.copyWithin()

// C and C'+'s memmove and is the high-performance method to shift a data of an Array
// copyWithin() method copies the part of the given array with its elements and returns the // modified array. This method doe'n't change the length of the modified array.

```js
let shows = [
  "Pink Panther",
  "Chhota Bheem",
  "Oggy",
  "Tom and Jerry",
  "Doraemon",
];
console.log(shows.copyWithin(2, 0, 2));
```

```js
console.log([21, 19, 46, 4, 5].copyWithin(-2)); // [21, 19, 46, 21, 19]
console.log([21, 19, 46, 4, 5].copyWithin(0, 3)); // [4, 5, 46, 4, 5]
console.log([21, 19, 46, 4, 5].copyWithin(0, 3, 4)); // [4, 19, 46, 4, 5]
```

---

### string to uppercase

```js
let data = "brōkən";
console.log(data.toLocaleUpperCase("en-US")); //
```

---

### JS Modules:

Separated parts of JS peaces of code following a pattern or convention.

How can you incorporate modules?

---

### Importing JSON Files via Static import Declarations

```js
// tsconfig.json
{
"compilerOptions": {
  "target": "es2015",
  "module": "commonjs",
  "strict": true,
  "moduleResolution": "node",
  "resolveJsonModule": true
  }
}
```

// We no longer need the "use strict" directive since
// all ECMAScript modules implicitly use strict mode.

```js
import * as express from "express";
import * as config from "./config.json";

const app = express();

app.listen(config.server.nodePort, () => {
  console.log(`Listening on port ${config.server.nodePort} ...`);
});
```

---

### Functions VS. Methods

Simply put, a `Function` is a piece of code that `can be called by its name`. It can be pass arguments and return values.
`Methods` is a piece of code that `must be called by its name` along with its associated object name'.

### Function

```js
const simple = (a) => {
  return a;
}; 
simple(5); // CAN called by its name
```

### Method

```js
const simple = (a) => {
 obj = {
  simple: (a) => {
    return a;
  },
};
obj.simple(5); // MUST be called by its name
```

---

### typeof bar === "object"

`null` is also considered an object so

```js
// ❌ instead of 💩
var bar = null;
console.log(typeof bar === "object"); // logs true! -> null object?

// better do ✅
var bar = null;
console.log(bar !== null && bar.constructor === Object); // logs false
```

---

### What's the difference between setTimeout() and setInterval()?

### Definitions:
> setTimeout() allows to run a function once after the interval of time.

> setInterval() allows to run a function regularly with the interval between the runs.

#### Running regularly:

One is setInterval(), the other one is a "recursive setTimeout()"

```js
// Recursive setTimeout
let timerId = setTimeout(tick() => {
  alert('tick');
  timerId = setTimeout(tick, 2000); // (*
}, 2000);
```

I can't even begin to tell you how many "JavaScript developers" I've interviewed who cannot answer this. I'm floored every time!

> setInterval() code executes every 1000ms exactly, while the setTimeout() waits 1000ms,runs the function, which takes some ms, then sets another timeout. So the wait period is actually greater than 1000ms. also, setInterval() execute infinite times after the interval

> setTimeout() execute one after the ms time

---

### Functions Rest Parameters: return (...args)

The rest parameter syntax allows us to represent an 'indefinite number of arguments as an array.'

```js
function sum(...args) {
  return args.reduce((previous, current) => {
    return previous + current;
  });
}
console.log(sum(1, 2, 3)); // 6
console.log(sum(1, 2, 3, 4)); // 10

function myFun(a, b, ...manyMoreArgs) {
  console.log(a, b, manyMoreArgs);
}
myFun("one", "two", "three", "four", "five", "six"); // "one" "two" Array ["three", "four", "five", "six"]
```

---

## Rest parameter and Spread operator

```js
const arr = ["hello", "world", 3, "bye", ":)", "!"];
const [val1, val2, ...rest] = arr;
const foo = (n) => {
  return n
    .filter((x) => {
      return x;
    })
    .join(" ");
};
val1; // "hello"
val2; // "world"
foo(rest); // "3 bye :) !"
```

---

## Combine multiple Arrays

```js
let a = [1, 2, 3];
let b = [4, 5, 6];
let sum = [...a, ...b, 7]; // [1, 2, 3, 4, 5, 6, 7]
```

---

## using meaningful names. Best practices

I need to think about what this function is doing. so I can read this line and immediately tell what's going on.

```js
const numbers = [1,2,3,4];

 // ❌ instead of 💩
numbers.filter(num => num % 2 === 0);

// better do ✅
const isEven = num => num % 2 === 0);
numbers.filter(isEven);
```

---

## Don't pass arguments from one function to another

There is no need to explicitly pass num.

```js
const numbers = [1, 2, 3, 4];
const multiplyByTwo = (num) => num * 2;

// ❌ instead of 💩
numbers.map((num) => multiplyByTwo(num));

// better do ✅
numbers.map(multiplyByTwo); // [2, 4, 6, 8]
```

---

### Use partial application

```js
const numbers = [1, 2, 3, 4];

// ❌ instead of 💩
const multiplyBy = (num, multiplier) => num * multiplier;
numbers.map((num) => multiplyBy(num, 2));

const multiplyBy = (multiplier) => (num) => num * multiplier;
// better do ✅
numbers.map(multiplyBy(2));
```

---

### Break long chains or Assign them to a variable/function

- Break the chain - assign the result of each line to a variable and operate on that variable.
- Assign the result to a function or a variable with a meaningful name.

```js
const employees = [{name:"bruce banner", age:21, salary: 1500}, ...];
const isAboveEighteen = (employ) => employ.age > 18;
const addRandomBonus = (employ) => ({...employ, salary: employ.salary*(Math.random() + 1)});
const toSumOfSalaries = (sum, employ) => sum + employ.salary;

// BAD - I need to think how each line effect the next one and what will be the outcome
employees
  .filter(isAboveEighteen)
  .map(addRandomBonus)
  .reduce(toSumOfSalaries);

// Breaking the chain
const aboveEighteenEmployees = employees.filter(isAboveEighteen);
const salariesWithBonus = aboveEighteenEmployees.map(addRandomBonus);
const sumOfSalaries = salariesWithBonus.reduce(toSumOfSalaries);

// Assign the result
// *If we need to reuse this then we would use a function
const aboveEighteenAfterBonusSumOfSalaries = employees
      .filter(isAboveEighteen)
      .map(addRandomBonus)
      .reduce(toSumOfSalaries);
```

---

### Rest & Spread JavaScript Objects

- Spread uses the same notation as rest: '...' What it does is quite different.
- Using object spread, you can merge both objects into a single new object (from left to right)

### spread an object into another object

```js
const point2D = { x: 1, y: 2 };
const point3D = { ...point2D, z: 3 };
console.log(point3D); // {x: 1, y: 2}
```

### spread shallow extend

```js
const foo = { a: 1, b: 2, c: 0 };
const bar = { c: 1, d: 2 };
/** Merge foo and bar */
const fooBar = { ...foo, ...bar }; // fooBar is now {a: 1, b: 2, c: 1, d: 2}
```

### clone and merge using ...spread

```js
var obj1 = { foo: "bar", x: 42 };
var obj2 = { foo: "baz", y: 13 };
var clonedObj = { ...obj1 }; // { foo: "bar", x: 42 }
var mergedObj = { ...obj1, ...obj2 }; // { foo: "baz", x: 42, y: 13 }
```

### merge objects

```js
const part1 = {
  color: "white",
};
const part2 = {
  model: "Honda",
};
const part3 = {
  year: 2005,
};

const car = {
  ...part1,
  ...part2,
  ...part3,
};
console.log(car); // { color: 'white', model: 'Honda', year: 2005 }
```

### spread modify objects

```js
const box = {
  color: "red",
  size: {
    width: 200,
    height: 100,
  },
  items: ["pencil", "notebook"],
};
```

```js
const biggerBox = {
  ...box,
  size: {
    ...box.size,
    height: 200,
  },
};
console.log(biggerBox);
/*
{
  color: 'red',
  size: {
    width: 200,
    height: 200 <--Updated value
  },
  items: ['pencil', 'notebook']
}
*/
```

```js
const blackBox = {
  ...box,
  color: "black",
  size: {
    ...box.size,
    width: 400,
  },
  items: [...box.items, "ruler"],
};
console.log(blackBox);
/*
{
  color: 'black', // Updated value
  size: {
    width: 400, // Updated value
    height: 100
  },
  items: ['pencil', 'notebook', 'ruler'] // A new item ruler
}
*/
```

### display partial Object rest properties

```js
const style = {
  width: 300,
  marginLeft: 10,
  marginRight: 30,
};

const { width, ...margin } = style;

console.log(width); // 300
console.log(margin); // { marginLeft: 10, marginRight: 30 }
```

### Shallow Copies of Objects

// Shallow Copies of Objects (ngrx issue: readonly fixed)
// BUT mutating the array will impact both todos

```js
const shallow = {
  text: "Water the flowers",
  completed: false,
  tags: ["garden"],
};
const shallowCopy = { ...shallow }; // ok :)
// BUT mutating the array will impact both todos
shallowCopy.tags.push("MUTATING WITH PUSH"); // tags: ["garden", "weekend"]
```

### Adding Properties to an Object

```js
const user = { id: 100, name: "Moon" };
const userWithPass = { ...user, password: "Password!" };
user; // { id: 100, name: 'Moon' }
userWithPass; // { id: 100, name: 'Moon', password: 'Password!' }
```

### Merge two objects into a new object (from left to right)

```js
// part1 and part2 are merged together into user1. 1)
const part1 = { id: 100, name: "Moon" };
const part2 = { id: 100, password: "Password!" };
const user1 = { ...part1, ...part2 }; // { id: 100, name: 'Moon', password: 'Password!' }
```

```js
const partial = { id: 100, name: "Howard Moon" };
const user = { ...partial, ...{ id: 100, password: "Password!" } };
user; // { id: 100, name: 'Howard Moon', password: 'Password!' }
```

### To clone and merge

```js
const obj1 = { foo: "bar", x: 42 };
const obj2 = { foo: "baz", y: 13 };

const clonedObj = { ...obj1 }; // Object { foo: "bar", x: 42 }
const mergedObj = { ...obj1, ...obj2 }; // Object { foo: "baz", x: 42, y: 13 }
```

### removed Object Properties

```js
const noPassword = ({ password, ...rest }) => rest;

const user = [
  {
    id: 100,
    name: "Howard Moon",
    password: "Password!",
  },
];
noPassword(user); //  { id: 100, name: 'Howard moon' }
```

---

### Access properties: `Object.keys` Vs `Object.values` Vs `Object.entries`

```js
const user = {
  name: "Leo",
  age: 30,
};

for (let key of Object.keys(user)) {
  console.log(key); //  name, age
}

for (let value of Object.values(user)) {
  console.log(value); // Leo, 30
}

for (let entry of Object.entries(user)) {
  console.log(entry); // ['name', 'Leo'], ['age', 30]
}
```

---

### rename keys from objects inside an array

```js
// use Object.values() to retrieve values and then array.reduce() to compose a new object
const customers = [{
    prop_name: "Negan",
    prop_age: 45,
    prop_weapon: "Bat",
    prop_email: "negan@sanctuary.com",
    prop_city: "Washington",
  },{
    prop_name: "Daryl",
    prop_age: 41,
    prop_weapon: "Crossbow",
    prop_email: "daryl.dixon@kickass.com",
    prop_city: "Atlanta",
  },{
    prop_name: "Rick",
    prop_age: 45,
    prop_weapon: "Magnum 357",
    prop_email: "rick@alexandria.com",
    prop_city: "King County",
  }];
const newKeys = ["firstname", "age", "weapon", "email", "city"];
let result = customers.map((obj) =>
  Object.values(obj).reduce((acc, cur, i) => {
    acc[newKeys[i]] = cur;
    return acc;
  }, {})
);

console.log(result);
// [
//  {firstname: "Negan", age: 45, weapon: "Bat", email: "negan@sanctuary.com", city: "Washington"}
//  {firstname: "Daryl", age: 41, weapon: "Crossbow", email: "daryl.dixon@kickass.com", city: "Atlanta"}
//  {firstname: "Rick", age: 45, weapon: "Magnum 357", email: "rick@alexandria.com", city: "King County"}
// ]
```

---

### FP methods: passing f() as arguments

```js
function add(x, y) {
  return x + y;
}
function subtract(x, y) {
  return x - y;
}
function doTheAction(arg1, arg2, action) {
  return action(arg1, arg2);
}

doTheAction(1, 3, add); // 4
doTheAction(3, 1, subtract); // 2
```

---

### FP keep the values private. return function

```js
function createCounter() {
  var count = 0;
  return {
    increment: function () {
      count += 1;
    },
    currentValue: function () {
      return count;
    },
  };
}
// NO access
createCounter().increment();
createCounter().currentValue(); // 0

// yep we have access
var myCounter = createCounter();
console.log(myCounter.currentValue()); // 0
myCounter.increment();
console.log(myCounter.currentValue()); // 1
```

---

### sum. Utility

```js
const sum = (...arr: number[]) => [...arr].reduce((acc, val) => acc + val, 0);

sum(1, 2, 3, 4); // 10
sum(...[1, 2, 3, 4]); // 10
```

---

### deepFreeze

```js
// is object
const isObject = (val) => val && typeof val === "object";

function deepFreeze(obj) {
  if (isObject(obj) && !Object.isFrozen(obj)) {
    Object.keys(obj).forEach((name) => deepFreeze(obj[name]));
    Object.freeze(obj);
  }
  return obj;
}
```

---

### isObject

```js
function isObject(obj) {
  return (typeof obj === "object" && obj !== null) || typeof obj === "function";
}

// random fucntion just for testing
function sumArguments() {
  return Array.from(arguments).reduce((sum, num) => sum + num);
}

isObject(sumArguments); //  true
```

---

## Regular Expression as the Search Expression (Single Match)

```js
var totn_string = "We Want to Replace the First Uppercase Character";

console.log(totn_string.replace(/[A-Z]/, "Y")); // Ye Want to Replace the First Uppercase Character
```

---

### extend a const and ovewrites the initial object

```js
extendingDateRangePickerDefaultConfig: CustomRangeDateRangePicker = {
  dateRanges: [{ id: "CUSTOM", label: "CUSTOM RANGE" }],
};

customDateRangePickerConfig: DateRangePickerConfig = Object.assign(
  {},
  dateRangePickerDefaultConfig,
  this.extendingDateRangePickerDefaultConfig
);
```

---

### Remove element from array

```js
const arr1 = ["a", "b", "c", "d", "e"];
const arr2 = arr1.filter((a) => a !== "e"); // ['a', 'b', 'c', 'd']
```

---

### Take the `MAX` and `MIN` value from Array

```js
[7, 4, 1, 99, 57, 2, 1, 100]
  .reduce((x, y) => (x > y ? x : y)); // 100
```

```js
let arr = [-1, 7, 2, null, -0, +0, 10];

highest = Math.max(...arr); // 10
```

```js
import { max } from "../math.js";
const nums = [1, 2, 3];

max(...nums); // 3
```


```js
var numbers = [1, 2, 3, 4];
Math.max.apply(null, numbers); // 4
```


```js
function arrayMax(array) {
  return array.reduce((a, b) => Math.max(a, b));
}
arrayMax([-1, 7, 2, null, -0, +0, 10]); // 10
```


```js
Rx.Observable.of(5, 4, 7, 2, 8)
  .min()
  .subscribe( function(x) {
      document.write(x);
  });

Rx.Observable.of(5, 4, 7, 2, 8)
  .min()
  .subscribe( function(x) {
  document.write(
```

LINK:
http://jsfiddle.net/leolanese/2dk6ahv5/

---

### Take the MIN number in the list

```js
[7, 4, 1, 99, 57, 2, 1, 100]
   .reduce((x, y) => (x < y ? x : y)); // 1
```

```js
let numbers = [9, 4, 7, 1];
Math.min(...numbers); // 1
```

```js
const array = [1, 2, 3, 4, 5]
[head, ...tail] = array

console.log(head, tail) // 1, [2,3,4,5]

const maxValue = Math.max(...array)
console.log(maxValue) // 5
```

---

## Replace element no-mutating

```js
const arr1 = ["a", "b", "c", "d", "e"];
const arr2 = arr1.map((item) => {
  if (item === "c") {
    item = "CAT";
  }
  return item;
}); // ['a', 'b', 'CAT', 'd', 'e']
```

---

## Fill an array with new objects

// When every item of the initialized array should be a new object, Array.from() is a better solution:

```js
const length = 3;
const resultA = Array.from({ length }, () => ({}));
const resultB = Array(length).fill({});

resultA; // [{}, {}, {}]
resultB; // [{}, {}, {}]

resultA[0] === resultA[1]; // false
resultB[0] === resultB[1]; // true
```

---

## Unique items of an array. Remove duplicates elements. utility

```js
const unique = (arr: any[]) => [...new Set(arr)];

unique([1, 2, 2, 3, 4, 4, 5]); // [1, 2, 3, 4, 5]
```

---

## Create a clone of the array, including all the nested ones

```js
const numbers = [
  [0, 1, 2],
  ["one", "two", "three"],
];
otherNumbers = [...numbers];
numbers[0] === otherNumbers[0]; // true
```

---

## Clone an array

> Array.from(numbers) creates a shallow copy of numbers array.

```js
const numbers = [3, 6, 9];
const numbersCopy = Array.from(numbers);

numbers === numbersCopy; // false
```

---

### Adding an item to an object

```js
let arr = [
  { a: 1, b: 2 },
  { a: 3, b: 4 },
  { a: 5, b: 6 },
];
target = arr.concat({ a: 7, b: 8 });
```

## Removing an item from an object

```js
// filter all items in the source except the one with the given id (a is the id/key)
let arr = [
  { a: 1, b: 2 },
  { a: 3, b: 4 },
  { a: 5, b: 6 },
];
n = arr.filter((x) => x.a !== 1); // {'a':3,'b':4}, {'a':5,'b':6}
```

## Updating an item

```js
// first we need to find the position of this item in the array
let arr = [ {'a':1,'b':2}, {'a':3,'b':4}, {'a':5,'b':6} ];

index = arr.findIndex(x => x.a === 3); // 1
[...arr.slice(0,index), {'x':666}, ...arr.slice(index + 1, arr.length)]
```

---

## Dynamic Import

```js
import { max } from "../math.js";
const nums = [1, 2, 3];
max(...nums); // 3
```

---

## fetch

```js
// async function
async function fetchAsync () {
  // await response of fetch call
  let response = await fetch('https://api.github.com');
  // only proceed once promise is resolved
  let data = await response.json();
  // only proceed once second promise is resolved
  return data;
}

// trigger async function
// log response or catch error of fetch promise
fetchAsync()
  .then(data => console.log(data))
  .catch(reason => console.log(reason.message))holder.typicode.com/todos')
  .then(response => response.json())
.then(data => console.log(JSON.stringify(data)))
```

---

## async/await function

```js
function logFetch(url) {
  return fetch(url)
  .then(response => response.text())
  .then(text => {
  console.log(text);
  }).catch(err => {
  console.error('fetch failed', err);
  });
}

// And here's the same thing using async functions: It's the same number of lines, but all the callbacks are gone.
async function logFetch(url) {
  try {
    const response = await fetch(url); // await operator wait for a Promise returned by an async function
    console.log(await response.text());
  }
```

### Used to Expand elements of an array in specific places

```js
// this
function myFunctions(x, y, z) {
  console.log(x);
  console.log(y);
  console.log(z);
}
const args = [0, 1, 2];
myFunctions(args);

// better do ✅
function myFunctions(x, y, z) {
  console.log(x);
  console.log(y);
  console.log(z);
}
myFunctions(...args);
```

---

## Assing conditinal for object creations using spread operator

```js
// ❌ instead of 💩
const newObj = {
  attr_1: attr_1,
  attr_2: attr_2,
};
if (condition1) {
  newObj["attr_3"] = attr_3;
}


// better do ✅
const newObj = {
  'attr_1': attr_1,
  'attr_2': attr_2,
  ...( condition1 ) ? {'attr_3': attr_3} : {}),
}
```

```js
// or even better
const insertIf = (condition, object) => (condition ? object : {});

const newObject = {
  attr_1: "1",
  attr_2: "2",
  ...insertIf(condition1, {
    attr_3: attr_3,
  }),
};
```

---

## remove the repeated elements inside an array

```js
const uniqueArr = (arr) => [...new Set(arr)];
uniqueArr([1, 2, 2, 2, 3, 4, 4, 5, 6, 7, 7]); // [1, 2, 3, 4, 5, 6, 7]
```

---

## Combine / union Arrays

```js
arr1.push(...arr2); // Adds arr2 items to end of array
arr1.unshift(...arr2); //Adds arr2 items to beginning of array
```

```js
var arr1 = ["two", "three"];
var arr2 = ["one", ...arr1, "four", "five"]; // ["one", "two", "three", "four", "five"]
```

```js
// Using Math Functions operation convination
let arr = [-1, 7, 2, null, -0, +0, 10];
highest = Math.max(...arr); // 10

let numbers = [9, 4, 7, 1];
Math.min(...numbers); // 1

// as parameters:
function restParameters(param, ...params) {
  return params;
}
console.log(restParameters("a", "b", "c")); // ['b', 'c']
```

```js
// to turn strings into Arrays:
let chars = [...("Jon" + "Doe")];
console.log(chars); // ["J", "o", "n", "D", "o", "e"]

// Expand elements of an array within another array:
let values = [1, 2, 4];
let some = [...values, 8]; // [1, 2, 4, 8]
let more = [...values, 8, ...values]; // [1, 2, 4, 8, 1, 2, 4]

// calling functions with arguments:
let values = [1, 2, 4];
doSomething(...values);
function doSomething(x, y, z) {
  // x = 1, y = 2, z = 4
}
```

```js
// concatenate
var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
arr1 = [...arr1, ...arr2];

// Spread in object literals
// It copies own enumerable properties from a provided object onto a new object.
var obj1 = { foo: "bar", x: 42 };
var obj2 = { foo: "baz", y: 13 };

var clonedObj = { ...obj1 };
// Object { foo: "bar", x: 42 }

var mergedObj = { ...obj1, ...obj2 };
// Object { foo: "baz", x: 42, y: 13 }

// Object spread
// simply add a property to an object without mutating the original:
const point2d = { x: 1, y: 2 };
const point3D = { ...point2d, z: 3 }; // {x: 1, y: 2, z: 3}

// simple shallow extend
const foo = { a: 1, b: 2 };
const bar = { c: 1, d: 2 };
/*Merge foo and bar */
const fooBar = { ...foo, ...bar };
```

---

#### Function overloading OOP

```js
// overload declaration
function sum(a: number, b: number): number;
function sum(a: string, b: number): number;
function sum(a: number, b: string): number;
function sum(a: string, b: string): number;

// overload definiton
function sum(a,b){
if(typeof a === "string"){
a = parseInt(a,10);
}
if(typeof b === "string"){
b = parseInt(b,10);
}
return a + b; // add to string (after parseInt them)
}
sum(1,2);
sum("1","2"); // send 2 strings

// calling same function
function foo(a, b, opts) {
console.log(a , b , JSON.stringify(opts));
}
foo(1, 2);
foo(3, 4, {"test":"equals", "bar":"tree"});
```

#### Use SPREAD operator (...) :

```js
let arr = [-1, 7, 2, null, -0, +0, 10];
let highest = Math.max(...arr); // 10

let chars = [...("Jon" + "Doe")];
console.log(chars); // ["J", "o", "n", "D", "o", "e"]
```

---

#### Use REST parameters:

```js
function restParameters(param, ...params) {
  return params;
}
console.log(restParameters('a', 'b', 'c')); // ['b', 'c']
```

---

### Lamda/fat arrow notation and this

Fat arrows fix it by capturing the meaning of this from the surrounding context

NON-arrow:
"this" in a non-arrow function will 'point to the object that is calling the function'.

```js
function Person(age) {
  this.age = age;
  this.growOld = function () {
    // this within the function is going to point to window
    this.age++;
  };
}
var person = new Person(1);
setTimeout(person.growOld, 1000); // calling the function
setTimeout(function () {
  console.log(person.age);
}, 1000); // 1, should have been 2
```

### arrow:

In arrow function, this always 'refers to the object that is directly outside of the function scope'.

```js
function Person(age) {
  this.age = age; // this is captured by the arrow function from outside function scope
  this.growOld = () => {
    this.age++;
  };
}
var person = new Person(1);
setTimeout(person.growOld, 1000);

setTimeout(function () {
  console.log(person.age);
}, 2000); // 2
```

---

### Validate parameter type as specific object using type guard 'in'

#### in

```js
interface A {
  a: number;
}
interface B {
  b: string;
}
interface C {
  c: Date;
}

function foo(x: A | B | C) {
  if ("a" in x) {
    alert("a");
  } else if ("b" in x) {
    alert("b");
  } else {
    alert("c");
  }
}

foo({ a: 123 }); // a
foo({ b: "Leo" }); // b
foo({ c: new Date(2017, 4, 4, 17, 23, 42, 11) }); // c
```

---

### within a string, count the number of occurances of a character / character counting and string-position

```js
const isTheCharacter = (n) => n === "o";
const str = "this is foo bar";

console.log([...str].filter(isTheCharacter).length); // 2
```

---

### count number of repeated values inside string

('[0,1,0,3,4,0];'.match(/[0-0]/g)||[]).length; // 3

---

## Enforcing Required Parameters. Guards by functions requiring argument

An alternative to assigning default values to function parameters is to throw an error if any required value is not present

```js
function requiredParam(param) {
  console.log("param is missing", param);
}

function createAvenger({
  avengerName = requiredParam("avengerName"),
  realName = "unknown",
} = {}) {
  return {
    avengerName,
    realName,
  };
}

const ironMan = createAvenger(); // Error: Required parameter avengerName is missing
```

---

## validate argument. guards

```js
function missingArgument() {
  throw new Error();
}

function callMenuItemFunction(item = missingArgument()) {
  if (item.link) {
    $location.url(item.link);
  } else {
    item.fn && $scope.$eval(item.fn);
  }
}
```

### guards as Rest parameters

```js
function join(separator, ...values) {
  return values.join(separator);
}

// all of the parameters after the first
// are gathered together into `values` which is a true `Array`
//  "one//two//three"
console.log(join("//", "one", "two", "three"));
```

### Guard as Default parameters

```js
function getData(data, useCache = true) {
  useCache
    ? console.log("using cache for", data)
    : console.log("not using cache", data);
}

// `useCache` is missing and is `undefined`.
// therefore `useCache`defaults to `true`
getData({ q: "churches+in+Pittsburg" });
```

---

## Micro-branching strategies: Guards (&&) and Defaults(||)

```js
// invoke callback if there is one
callback && callback();

// delay by argument or 20
delayBy(delay || 20);

// if x is undefined assign then 10
const x = x || 10;

// remove node from its parent
node && node.parent && node.parent.removeChild(node);

// log a test in the console id we have one
window.console && console.log("test");
```

---

## Guards and paramenter validation

### typeof type guards

```js
function isNumber(x: any): x is number {
    return typeof x === "number";
}

function isString(x: any): x is string {
    return typeof x === "string";
}

function padLeft(value: string, padding: string | number) {
    if (isNumber(padding)) {
        return Array(padding + 1).join(" ") + value;
    }
    if (isString(padding)) {
        return padding + value;
    }
    throw new Error(`Expected string or number, got '${padding}'.`);
}
```

---

### Validate argument passed to function or `null` using `Type guards` & `type assertions`. MB

```js
// ❌ instead of 💩
function foo(stringOrNull: string | null): string {
  if (stringOrNull === null) {
    return "null value";
  } else {
    return stringOrNull;
  }
}

// better do ✅
function foo(stringOrNull: string | null): string {
  return stringOrNull ?? "null value";
}
```


---

## Required parameters. guards

- Gets called if a parameter is missing and the expression
- specifying the default value is evaluated.

```js
function throwIfMissing() {
  throw new Error("Missing parameter");
}

function func(requiredParam = throwIfMissing()) {
  // some implementation
}
```

### guards missing Params function

```js
function missingParams() {
  loggingService.log.warn(CONconsole_NAME + ": incident cannot be processed.");
}

function processIncident(incident = missingParams()) {
  if (incident.type === "incident" && incident.assignmentStatus === "New") {
    console.log("all good here!");
  }
}
```

---

## Null vs. Undefined

```js
null: null is an empty or non-existent value. null must be assigned: null is an
assigned value. It means nothing.
```

```js
undefined: undefined typically means a variable has been declared but not defined yet.
```

#### In common:

```js
Both null and undefined are primitive values. null and undefined are falsy values. 

null and undefined are both primitives. However an error shows that 

typeof null = object. null !== undefined but null == undefined.
```

---

### Copy 2 elements

```js
let a = "Leo";
let b = "Lanese";

a = (
  (x) => () =>
    x
)(b)((b = a));

a; // Leo
b; // Lanese
```

---

### combine multiple arrays using Spread

```js
let a = [1, 2, 3];
let b = [4, 5, 6];

// ❌ instead of 💩
// do not use concat
let sum = a.concat(b, 7); //[1, 2, 3, 4, 5, 6, 7]

// better do ✅
// Spread
let sum2 = [...a, ...b, 7];
```

### Copying Arrays

```js
var arr = [1, 2, 3];
var arr2 = [...arr]; // like arr.slice()

arr2.push(4);
```

### Combine Arrays

```js
var arr1 = ["two", "three"];

arr2 = ["one", ...arr1, "four", "five"]; // ["one", "two", "three", "four", "five"]
```

### Using Math functions: getting the max

```js
var numbers = [9, 4, 7, 2];
Math.max(...numbers); // 9
```

---

### Conditionally adding elements inside Array literals

```js
const cond = false;

arr = [...(cond ? ["a"] : []), "b"]; // ["b"]
```

### conditionals

```js
const cond = true;

[...(cond ? ["a"] : ["b"])]; // ['a']
```

### conditional Object literal

```js
const cond = false;

obj = { ...(cond ? { a: 1 } : { b: 2 }), c: 3 }; // {b: 2, c: 3}
```

---

### Declare Objects as Objects:

```js
// ❌ instead of 💩
var service = {};
service.winJsApp = null;
service.winJSActivation = 1;
service.actions = {
  goToView: "goToView",
  goToModal: "goToModal",
};
```

```js
// better
// object properties are declared using object literal syntax
const service2 = {
  winJsApp: null,
  winJSActivation: 1,
  actions: {
    goToView: "goToView",
    goToModal: "goToModal",
  },
};
```

---

## Higher Order Functions. HoF

> Any function which takes function as an argument, or any function which returns a function is known as a higher order function.
> An example of pre-defined higher order functions (HoF): `reduce()`, `reject()`, `find()`, `reduce()`, etc
> As functions are first-class citizens they are just like any other type of data, which can be stored, accessed, passed as arguments, and even returned from another method!
> The function `greeting()` is a higher order function that takes another function and a string as a parameter. 

```js
const hightOrderFunction = (callback) => {
  return callback()
}
```

```js
// normal functions
const toEnglish = (name) => `Hello ${name}`;
const toSpanish = (name) => `Hola ${name}`;
const toItalian = (name) => `Ciao ${name}`;

// Our higher order function
const sayWords = (toTranslate, name) => toTranslate(name);

sayWords(toItalian, "Leo"); // 'Ciao Leo'
```

## Pick only one property using map with Higher order functions. HoF

```js
// Map return the same objects but transform
const ao = [{
    name: "Leo",
    age: 26,
  },
  {
    name: "Tom",
    age: 7,
  },
  {
    name: "Sam",
    age: 5,
  }];
arr = ao.map((a) => a.name); // ['Leo', 'Tom', 'Sam']
```

```js
// even better using FP + ES6:
var arr = ao.map(a => a.name);
```

### Immutable

These functions do not mutate their arguments, but produce new instances every time they are called.

### Why we need it?

Create the same functionality with less code: less code means less bugs!
Allow as to put a function within another function and group tiny functions.

---

### First class and higher order functions (HoF):

```js
// higher order function
var funcAsValue = function(y) {
  return y _ 4;
};

// higher order function
var returnFunc = function(z) {
  return function(a) {
    return a _ z;
  };
};

// First class
var funcAsArgument = function(a, func) {
  return func(a);
};
```

---

### Using Recursion instead for or while loops

A recursive function is a function that quite simply calls itself

```js
Ej1)
function loop(i) {
  console.log("i is " + i)
  if (i < 10) {
    loop(i + 1)
  }
}
loop(0);
```

```js
Ej2)
var recursive = function(n) {
  if (n < 1) {
    return n;
  } else {
    return recursive(n - 1);
  }
};
```

```js
Ej3) // So instead using loops:
var factorial = function(n) {
  var result = 1;
  for (var x = 1; x <= n; x += 1) {
    result = x *esult;
  }
  return result;
};

factorial(5) // 120
```

```js
Ej 4)
// A stateless approach would be:
var recursiveFactorial = function(n) {
  if (n < 2) {
    return n;
  } else {
    return n *ecursiveFactorial(n - 1);
  }
};
recursiveFactorial(5) // 120
```

```js
Ej 5) counter example:
var counter = 10;
while(counter > 0) {
  console.log(counter--);
}

// usign recursion countdown:
var countdown = function countdown(a) {
if (a === 0) return;
  console.log(a)
  countdown(a - 1); // recursive call
  }
};

countdown(10); //
```

---

### Currying

Since Javascript has higher order functions we can call functions with some of its arguments pre-filled


```js
const curry = (fn: Function, arity = fn.length, ...args: any[]): any => arity <= args.length ? fn(...args) : curry.bind(null, fn, arity, ...args);

const removeFalsy = curry(compact, 2)(Boolean);
const removeNull = curry(compact, 2)((v: any) => v !== null);
```

```js
var bindExample = function (a, b) {
  return a / b;
};
var test = bindExample.bind(null, 3);
```

// Here test creates a new function which when invoked already has the a argument filled in as 3, then will be: 3 / 4

```js
test(4); // 0.75
```

---

### Memoisation

Functions that are expensive to run can be optimised with memoisation. This involves using a closure to cache the results of previous calls to the function

```js
// ej1
var memoise = function(func) {
  var cache = {};
    return function(arg) {
    if (arg in cache) {
     console.log(arg + ' in cache');
     return cache[arg];
    } else {
      console.log(arg + 'not in cache');
      return cache[arg] = func(arg);
    }
  };
};

var memo = memoise(function(n) {
  return n *;
});

console.time("not in cache");
memo(1) // 2 (1 not in cache)
console.timeEnd("not in cache");
console.time("cache");
memo(1) // 2 (1 in cache)
console.timeEnd("cache");
```

```js
// ej2. Angular
cache = {};

memoise = (fn) => {
  return (...args) => {
    const n = args[0]; // Array(31005)
    return n in this.cache ? this.cache[n] : (this.cache[n] = fn(n));
  };
};

getListTotal = (): number | string => {
  const validateTotalListItemsFound = (n) => this.listing?.getFinalModels();
  const memoised = this.memoise(validateTotalListItemsFound);
  const totalListItemsFound = memoised(this.listing?.getFinalModels());

  return totalListItemsFound
    ? Object.keys(totalListItemsFound).length
    : "No results";
};
```

---

### Thunks and trampolines:

A thunk is much like a continuation except that it is stored as a data structure for use at a later time. A trampoline manages the execution and return values of thunks
(so called because it bounces thunks around).
In Javascript we can represent a thunk as follows:

```js
var thunk = function (f, lst) {
  return { tag: "thunk", func: f, args: lst };
};

var thunkValue = function (x) {
  return { tag: "value", val: x };
};
```

Passing Functions as Parameters to Another Function:
We have established that a function can be stored in (actually, assigned to) a variable,
these variables can be passed as parameters to another function. So, instead of executing the function and passing the result as a parameter to the function, the entire function declaration can be passed as a parameter.

- Summary:
  A function is just a declaration until it is explicitly evaluated.
  The declaration can be assigned to a variable, which can then be passed as a parameter to another function.
  So, a JavaScript Function is a JavaScript Variable until it is executed (evaluated).

---

### Testing for Undefined Variables

```js
typeof foo !== "undefined";
```

> check whether SomeImportantThing has been initialised

```js
if (!SomeImportantThing) {
  // FAIL
  var SomeImportantThing = {};
}
```

```js
var SomeImportantThing;
// make sure it's there
if (!SomeImportantThing) {
  SomeImportantThing = {};
}
```

---

### Objects as a Data Type

```js
const foo = {}; // a new empty object
```

Using an object literal - {} notation - it is possible to create a plain object.
This new object inherits from Object.prototype and does not have own properties defined.

// a new object with a 'test' property with value 12

```js
const bar = { test: 12 };
```

---

### Objects Accessing Properties

The properties of an object can be accessed in two ways:

- dot notation
- square bracket notation.

```js
var foo = {name: 'kitten'}
foo.name; // kitten
foo['name']; // kitten

var get = 'name';
foo[get]; // kitten

foo.1234; // SyntaxError
foo['1234']; // works
```

---

### Deleting Property from Object

`undefined` or `null` only removes the value associated with the property, but not the key.

```js
var obj = {
  bar: 1,
  foo: 2,
  baz: 3,
};
obj.bar = undefined;
obj.foo = null;
delete obj.baz;

for (var i in obj) {
  if (obj.hasOwnProperty(i)) {
    console.log(i, "" + obj[i]);
  }
}
```

---

### validate properties on Object: hasOwnProperty

```js
var foo = {};
foo.bar = "10";

foo.hasOwnProperty("bar"); // true
```

```js
var foo = {
  bar: "Here be dragons",
};
foo.hasOwnProperty("bar"); // true
```

---

### Use {} instead new:

```js
Old: var a = new Array();
var o = new Object();
```

```js
New: var a = Array(); // or var a3 = []
var o = {};
1;
```

---

### setTimeout: Manually Clearing Timeouts

function foo() {}
var id = setTimeout(foo, 1000);
clearTimeout(id);

---

### Validate Object namespace keys/properties: this && this && this .... :(

```js
var obj = {
  bar: 1,
  foo: 2,
  baz: {
    joz: 3,
  },
};
obj && obj.hasOwnProperty("baz") && obj.baz.hasOwnProperty("joz");
```

```js
// or
obj && obj.baz && obj.baz.joz;
```

```js
// or
typeof obj !== "undefined" &&
  !!obj.baz.jaz2 &&
  obj.baz.jaz2.hasOwnProperty("jaz3");
```

```js
// or better
try {
  obj.baz.jaz2.hasOwnProperty("joz3");
} catch (e) {
  console.log("ERROR validation!");
}
```

```js
// even better
const name1 = obj && obj.baz ? obj.baz.joz : null; // 3
const name2 = obj && obj.baz ? obj.baz.jaz2 : null; // undefined (no error)
```

```js
// even better
// Unfortunately, you cannot access nested arrays with this trick
const name3 = ((obj || {}).baz || {}).joz; // 3
```

---

### Check if property is in a Object

```js
var myObject = {
  name: '@tips_js'
};

if (myObject.name) { ... }
```

// Even better: We can us" "in operat"r" an" "Object.hasOwnPrope"t"

```js
var myObject = {
  name: "@tips_js",
};

myObject.hasOwnProperty("name"); // true
"name" in myObject; // true

myObject.hasOwnProperty("valueOf"); // false valueOf inherited from the prototype chain
"valueOf" in myObject; // true
```

---

### Reflexion:

An object can look at itself, listing and changing its properties and methods

---

### Single Responsibility Principle

Honouring the Single Responsibility Principle:
developing components in isolation makes it a lot easier to write code. Unit tests written in TDD should never test a component's dependencies, which means they must be possible to replace with fakes.

AJS Factories should have a single responsibility, SRP that is encapsulated by its context. Once a factory begins to exceed that singular purpose, a new factory should be created.

---

### use void 0 instead "undefined":

```js
alert(undefined); //alerts "undefined" var undefined = "new value"; alert(undefined) //alerts "new value"
```

you cannot safely rely on undefined having the value that you expect.

void, on the other hand, cannot be overridden. void 0 will always return undefined

---

## Default Parameter Values

```js
function foo(x, y) {
  x = x || 11;
  y = y || 31;
  console.log(x + y);
}

foo(); // 42
foo(5, 6); // 11
foo(5); // 36
foo(null, 6); // 17Th
```

// better use ES6

```js
var doWork = function (name = "Leo") {
  return name;
};
```

---

## Enforcing mandatory parameters via parameter default values: (missing parameter)

```js
function missingParams() {
  loggingService.log.warn(controllerName + ": incident cannot be processed.");
}

function goToIncident(incident = missingParams()) {
  incidentServiceUtil.getIncidentDatabaseId(incident).then(
    (incidentDatabaseId) => {
      $state.go("incidentDetail", { incidentDatabaseId: incidentDatabaseId });
    },
    (error) => {
      loggingService.log.warn(
        controllerName + ": unable to retrieve incident." + error
      );
    }
  );
}
```

---

## Initialize / Handling Missing Parameters

```js
function createAvenger({
  avengerName = "unknown",
  realName = "unknown",
  height = 0,
  weight = 0,
  age = 0,
} = {}) {
  return {
    avengerName,
    realName,
    height,
    weight,
    age,
  };
}
const ironMan = createAvenger();

// ironMan = {
//  avengerName: 'unknown',
//  realName: 'unknown',
//  height: 0,
//  weight: 0,
//  age: 0;
// }

// Output ironMan:
ironMan; // {avengerName: "unknown", realName: "unknown", height: 0, weight: 0, age: 0}
```

---

## Types of function invocation

We need to pay close attention to the context in which a function is executing.

As a global function—The reference to this is set either to the global object or
to undefined (in strict mode):

```js
function doWork() {
  this.myVar = "Some value";
}
doWork();
window.myVar; // "Some value"
```

> Calling doWork() globally causes that "this" reference to point to the global object.

As a method—The reference to this is set to the owner of the method. This is an important part of JavaScri't's object-oriented nature:

```js
var obj = {
  prop: "Some property",
  getProp: function () {
    return this.prop;
  },
};
obj.getProp();
```

Invoking an objects method point this to the owning object.

## As a constructor by prepending the call with new

```js
function MyType(arg) {
  this.prop = arg;
}
var someVal = new MyType("some argument");
```

---

## Remove item from Array without knowing the index

```js
// apple = 0, orange = 1, pineapple = 2, banana = 3
const myArr = ["apple", "orange", "pineapple", "banana"];

const banana = myArr.indexOf("banana");

if (banana != -1) {
  myArr.splice(banana, 1);
}

console.log(myArr); // ["apple", "orange", "pineapple"]
```

---

## Arrow notation length of each element

```js
const elements = ["Hydrogen", "Helium", "Lithium", "Beryllium"];
elements.map(({ length }) => length); // [8, 6, 7, 9]
```

---

## assigning values using Rest

```js
const fn = (...args) => console.log(args);

fn(1, 2, 3); //[1, 2, 3]
fn("one", "two"); //['one', 'two']
```

---

## Setting a Default for Named Parameters

```js
function setPageThread(name, { popular, expires, activeClass } = {}) {
  console.log("Name: ", name);
  console.log("Popular: ", popular);
  console.log("Expires: ", expires);
  console.log("Active: ", activeClass);
}

// We can now safely invoke this function without its second argument
setPageThread("Leo!");
// Name: Leo!
// Popular: undefined
// Expires: undefined
// Active: undefined
```

---

## Spread Operator

> Spread uses the same notation as rest: '...' What it does is quite different.
> Using object spread, you can merge both objects into a single new object (from left to right)
> The spread operator allows us to split (or spread) an Array argument into individual elements.

```js
displayTags(...tags); // we have individual argument not and array
```

```js
const rotate = ([first, ...rest]) => [...rest, first];

console.log(rotate([1, 2, 3])); // [2, 3, 1]
```

```js
const arrToObj = ([key, value]) => ({ [key]: value });

console.log(arrToObj(["foo", "bar"])); // { "foo": "bar" }
```

---

## Using Named Parameters

```js
// declare which argument will be local var
function setPageThread(name, { popular, expires, activeClass }) {
  console.log("Name: ", name);
  console.log("Popular: ", popular);
  console.log("Expires: ", expires);
  console.log("Active: ", activeClass);
}

setPageThread("Leo", {
  popular: true,
  expires: 10000,
  activeClass: "is-active",
});

// Name:  Leo
// Popular:  true
// Expires:  10000
// Active:  is-active
```

---

## Split string using

> displayTags( ...tags); // we have individual argument not and array

```js
// Ej1:
const rotate = ([first, ...rest]) => [...rest, first];

console.log(rotate([1, 2, 3])); // [2, 3, 1]
```

```js
// Ej2:
const arrToObj = ([key, value]) => ({ [key]: value });

console.log(arrToObj(["foo", "bar"])); // { "foo": "bar" }
```

---

## define functions in JavaScript shorthands

> `fat arrow/lambda => ES5 -> ES6+`

```js
// FE and Angular
private getFeatureFlagsRepeatTransferCard(): boolean {
  return this.featureFlagsService.isEnabled(FeatureFlag.REPEAT_TRANSFER_CARD)
}

private getFeatureFlagsRepeatTransferCard = (): boolean => 	  this.featureFlagsService.isEnabled(FeatureFlag.REPEAT_TRANSFER_CARD);
```

```js
// FE & Angular
touchEvent = (first : string, last : string): void => {
    console.log(first, last)
  };
```

```js
// FE & Angular
logVWOConvertsion = (): ExperimentVariant =>
    this.vwoService.getExperimentVariant(94) ??  this.vwoService.logVWOConvertsionId(215);
```


```js
// Function Declaration. FD
function fullName(first : string, last :string) : string {
  return first + ' ' + last;
}

// Function Expression. FE
const otherFullName : (first : string, last : string) => string;

otherFullName = function (first : string, last : string) {
  return first + ' ' + last;
}

const thirdFullName : (first : string, last : string) => string function (first : string, last : string) {
  return first + ' ' + last;
}

console.log(fullName('Leo', 'Lanese'));
console.log(otherFullName('Leo', 'Lanese'));
console.log(thirdFullName('Leo', 'Lanese'));
```

```js
// IIFE
(function () {
  // code goes here...
})();
```

```js
(() => {
  // code goes here...
})();
```

```js
f = (function () {
  return function () {
    return "IIFE";
  };
})();
alert(f());
```

```js
var Init;
(Init = function Init() {
  alert("wee");
})();
```

```js
// function expression: ANONIMOUS function (no IIFE)
(function () {});
() => {};
```

```js
// FE with assignation
foo = () => {};
```

```js
// Function Statement:
function foo() {}
var myFn = function (x) {
  return x + 1;
};
let myFn = (x) => {
  return x + 1;
};
```

```js
// Function Expression:
var foo = function () {};
let foo = () => {};
```

```js
function sayMyName(name) {
  alert(`Hello ${name}`);
}
const sayMyName = (name) => {
  alert(`Hello ${name}!`);
};
sayMyName("Leo");
```

```js
var a = function a() {};
const a = () => {};
```

```js
var a = function a(b) {
  return b;
};
var a = (b) => b;
```

```js
var sum = function sum(a, b) {
  return a + b;
};
let sum = (a, b) => a + b;
```

---

### The Object Initializer Shorthand

```js
function buildUser(first, last) {
  let fullName = first + " " + last;
  return { first, last, fullName };
}

let user = buildUser("Leo", "Lanese");
console.log(user.first); // Leo
console.log(user.last); // Lanese
console.log(user.fullName); // Leo Lanese
```

---

### Shallow copy

Object spread does a shallow copy of the object. Only the object itself is cloned, while nested instances are not cloned.

```js
const laptop = {
  name: "MacBook Pro",
  screen: {
    size: 17,
    isRetina: true,
  },
};
const laptopClone = {
  ...laptop,
};

console.log(laptop === laptopClone); // false
console.log(laptop.screen === laptopClone.screen); // true
```

```js
const laptopDeepClone = {
  ...laptop,
  screen: {
    ...laptop.screen,
  },
};

console.log(laptop === laptopDeepClone); // false (no deep clone)
console.log(laptop.screen === laptopDeepClone.screen); // false (no deep clone)
```

---

## Issues With Scope in Callback Functions

The Anonymous functions passed as callbacks to other functions create their own scope

```js
function TagComponent(target, urlPath) {
  this.targetElement = target; // The scope of the TagComponent object is not the same as
  this.urlPath = urlPath;
}
TagComponent.prototype.render = function () {
  getRequest(this.urlPath, function (data) {
    let tags = data.tags;
    displayTags(this.targetElement, ...tags); // the scope of the anonymous function, this returns undefined
  });
};
```

### Solution

Using Arrow Functions to Preserve Scope
Arrow functions bind to the scope of where they are defined, not where they are called.
Arrow functions bind to the lexical scope this now properly refers to the TagComponent object (also known as lexical binding)

```js
function TagComponent(target, urlPath) {
  this.targetElement = target;
  this.urlPath = urlPath;
}
TagComponent.prototype.render = function () {
  getRequest(this.urlPath, (data) => {
    // fat arrow bind to the lexical scope
    let tags = data.tags;
    displayTags(this.targetElement, ...tags); // this now property refers to the TagComponent Object
  });
};
```

---

### Dynamically access object property using variable: `.` and `[]`

There are two ways to access properties of an object:

- Dot notation: something.bar
- Bracket notation: something['bar']

```js
// we can use this is the second value is also dynamic array
x.items[itemsByGroup[0]];

x?.items[itemsByGroup[0]];
```

---

### EXTENDING OBJECTS

```js
ES6JS | AJS/ATS | $
.assign()   .extend()     $.extend()
.merge()    mix()
```

```js
Object.assign():

let defaults = {
  container: ".main",
  isActiveClass: ".is-active"
};

let options1 = {
  container: ".main-container",
  isActiveClass: ".is-active-element"
};

let options2 = {
  isActiveClass: ".is-active-content",
  aNewClass: "somethingHere"
};

settings = Object.assign({}, defaults, options1, options2);
// Object {container: ".main-container", isActiveClass: ".is-active-content", aNewClass: "somethingHere"}
console.log(settings.container); // ".main-container"
```

- Get merge:
  angular.merge() (preserving properties in child objects):

> It does a deep copy of all properties from source to destination preserving properties in child objects. Note how we can also use multiple source objects that will be merged in order:

```js
var person1 = {
  name: "John",
  address: {
    description: "Oxford Street",
  },
};
var person2 = {
  id: 1,
  address: {
    postcode: "SW1",
  },
};
var extended = angular.extend(person1, person2); // it will replace similar keys
var merged = angular.merge(person1, person2); // ALL the key WILL PREVAIL
```

### extended object

```js
{
  id: 1,
  name: 'John',
  address : {
    postcode: 'SW1'
  }
}
// merged object
{
  id: 1,
  name: 'John',
  address : {
    description: 'Oxford Street',
    postcode: 'SW1'
  }
}
```

### extend()


```js
// is jQuery function this will replace similar keys

var defaults = { d1: false, d2: 5, d3: "foo" };
var options = { d4: true, d6: "bar" };

// jQuery Merge object2 into object1 (modifying there results)
$.extend( defaults, options );
Object {d1: false, d2: 5, d3: "foo", d4: true, d6: "bar"}

var defaults = { validate: false, limit: 5, name: "foo" };
var options = { validate: true, name: "bar" };

// Merge defaults and options, without modifying defaults
settings = $.extend( {}, defaults, options );
Object {validate: true, limit: 5, name: "bar"}
```

---

### JS shorthand: from ES5 -> ES6+

```js
// ❌ instead of 💩
// IIFE
(function () {
  // code goes here...
})();

// better do ✅
(() => {
  // code goes here...
})();
```

```js
// ❌ instead of 💩
// function expression: ANONIMOUS function (no IIFE)
(function () {});

// better do ✅
() => {};
```

```js
// ❌ instead of 💩
function foo() {}
const myFn = function (x) {
  return x + 1;
};

// better do ✅
let myFn = (x) => {
  return x + 1;
};
```

```js
// instead of
// Function Expression:
var foo = function () {};

// better do ✅
let foo = () => {};
```

```js
// ❌ instead of 💩
function sayMyName(name) {
  console.log(`Hello ${name}`);
}
sayMyName("Leo"); // Hello Leo

// better do ✅
const sayMyName = (name) => {
  console.log(`Hello ${name}!`);
};
sayMyName("Leo"); // Hello Leo
```

```js
// ❌ instead of 💩
var a = function a() {};

// better do ✅
const a = () => {};
```

```js
// ❌ instead of 💩
var a = function a(b) {
  return b;
};

// better do ✅
var a = (b) => b;
```

```js
// ❌ instead of 💩
var sum = function sum(a, b) {
  return a + b;
};

// better do ✅
let sum = (a, b) => a + b;
```

---

## curry a function. utility

```js
type Func<T = any> = (...args: T[]) => any;

const curry = (fn: Func, arity = fn.length, ...args: any[]): any =>
  arity <= args.length ? fn(...args) : curry.bind(null, fn, arity, ...args);

curry(Math.pow)(2)(10); // 1024
curry(Math.min, 3)(10)(50)(2); // 2
```

---

## dynamic Creating Object Literal with FP using curring

```js
const giveProp = (propName, prop, obj) =>
  Object.assign({}, obj, { [propName]: prop });

const curry = (func, arg) => {
  return (...args) => func(arg, ...args);
};

const giveName = curry(giveProp, "name");
const giveJob = curry(giveProp, "job");
const giveHero = curry(giveProp, "hero");

const solo = giveJob("smuggler", giveName("Han", {})); // { name: 'Han', job: 'smuggler' }
const ren = giveHero("Lanese", giveName("Leo", {})); // { name: 'Leo', hero: 'Lanese' }
```

---

## get the most frequent repetead element in an array

```js
const mostFrequent = (arr) =>
  Object.entries(
    arr.reduce((a, v) => {
      a[v] = a[v] ? a[v] + 1 : 1;
      return a;
    }, {})
  ).reduce((a, v) => (v[1] >= a[1] ? v : a), [null, 0])[0];

mostFrequent(["a", "b", "a", "c", "a", "a", "b"]); // 'a'
```

---

## Check if array contains all/every elements of another array

```js
let array1 = [1, 2, 3],
  array2 = [1, 2, 3, 4],
  array3 = [1, 2];

let checker = (arr, target) => target.every((v) => arr.includes(v)); // ES7 every & includes

console.log(checker(array2, array1)); // true
console.log(checker(array3, array1)); // false
```

---

## check if element is contained on few arays

```js
const name = ["ball", "bat", "glove", "glove", "glove"];
const price = [0, 2, 3, 1, 2, 1]; // 0 here
const weight = [2, 5, 1, 1, 1];

const cero = [0]; // what we are looking for

let checker = (arr, target) => target.every((v) => arr.includes(v));

console.log(checker(name, cero)); // false
console.log(checker(price, cero)); // true
console.log(checker(weight, cero)); // false
```

---

## Assigning values to multiple variables

```js
// instead of 
let a, b, c; 
a = 5; 
b = 8; 
c = 12;

// better do 
let [a, b, c] = [5, 8, 12];
```

---

## Object that contains an array: access array in to object.

```js
// define
var foo = {
  bar: ["foo", "bar", "baz"],
};

// access
foo.bar[2]; // will give you 'baz'
```

---

## `for...of` Vs `for...in` Vs forEach loops

Difference it boils down to what are we looking for: object, key properties, arrays, set, map or values or index(s)

```js
for...of to access the array entries
for...in to access the indexes of an array and the keys when used on an object literal
```

### for...of loop

iterates over: Array, arguments, Set, Map and "custom iterable objects like generatos".

> IF WE NEED TO iterate Objects (for): we use for..in. The 'for..of'

```js
const arr = [3, 5, 7, 9],
      obj = { a: 1, b: 2, c: 3 },
   objArr = [{ a: 1 }, { b: 2 }, { c: 3 }]

for (let n in arr) {
  console.log(n)
}; // 3,5,7,9 <- OK

for (let n of obj) {
  console.log(n)
}; // ERROR: Uncaught TypeError: obj is not iterable

// get indexs
for (const [i, v] of objArr.entries()) {
  console.log(i, v) // Prints "0 a", "1 b", "2 c"
}; {a: 1},{b: 2}, {c: 3}
```

### for...in loop

- iterates over an Array but "we get indexes, NOT values".
- iterates over Objects, but returns the property names/keys, not values.

### In brief:<br>

- This enhanced the old "for..in" loop and ".forEach" <br>
- Remember we cannot iterate an object using for..of<br>

```js
const arr = [3, 5, 7, 9],
      obj = { a: 1, b: 2, c: 3 };
objArr = [{ a: 1 }, { b: 2 }, { c: 3 }];

for (const p in arr) {
  console.log(p);
} // 0,1,2,3 (return index(s))

for (const p in obj) {
  console.log(p);
} // a,b,c (return properties/keys not values)

for (const p in objArr) {
  console.log(p);
} // 0,1,2 (return index(s))
```

```js
const arr = [3, 5, 7, 9],
  obj = { a: 1, b: 2, c: 3 };
objArr = [{ a: 1 }, { b: 2 }, { c: 3 }];

for (let n of arr) {
  console.log(n); // return
} // 3,5,7,9

for (const key of obj) {
  console.log(key);
} // ERROR

for (const n of arrObj) {
  console.log(n); // return
} // ERROR
```

### for..of with Map

```js
// Maps
const m = new Map([
  ["foo", "hello"],
  ["bar", "world"],
]);

for (const [name, value] of m) {
  console.log(name + "->" + value); //"foo->hello", "bar->world"
}
```

### for..of with Set

```js
// Sets
const s = new Set(["foo", true, 42]);

for (const value of s) {
  console.log(value); // 'foo', true, 42
}
```

### for..of with Generators

```js
// Generators
function* foo() {
  yield "foo";
  yield false;
  yield 42;
  yield "bar";
}

for (const v of foo()) {
  console.log(v); // 'foo', false, 42, 'bar'
}
```

### .forEach()

only iterates over arrays, it can access both the value and the index of each element while iterating.

```js
['a', 'b', 'c'].forEach(
  val => console.log(val); // a, b, c (array values)
);

['a', 'b', 'c'].forEach(
  (val, i) => console.log(i); // 0, 1, 2 (array indexes)
);
```

The forEach method calls the provided function once for every array element in the order.

```js
index = 0;
array = [1, 2, 3, 4, 5, 6];

array.forEach(myFunction);
function myFunction(item, index) {
  console.log(item); // 1 2 3 4 5 6
}
```

### LINKS

- My favorite search engine is [Duck Duck Go](https://duckduckgo.com).
- [for-vs-for-each-vs-for-in-vs-for-of-in-javascript](https://thecodebarbarian.com/for-vs-for-each-vs-for-in-vs-for-of-in-javascript)
- [javascript-for-in-for-of-foreach](https://www.30secondsofcode.org/blog/s/javascript-for-in-for-of-foreach)

---

## FP: Pure functions, currying, and composition

### Pure Functions

> A pure function is a function that when given a specific input will always return the same output, without causing side effects.
> This means that a pure function cannot:access closure variables, mutate input values, cannot do anything other than return a new value.
> Basically, a pure function should not modify its inputs or any variables in its closure scope.

```js
// With side effect (Impure):
let min = 60;
const isLessThanMin = (value) => value < min;

// pure
const isLessThanMin = (min, value) => value > min;
```

```js
// impure
const squares = (nums) => {
  for (let i = 0; i < nums.length; i++) nums[i] **= 2;
};

// pure
const squares = (nums) => nums.map((num) => num * num);
```

```js
// impure
// mutation on passed user reference
const updateUserAge = (user, age) => {
  user.age = age;
};

// pure
const updateUserAge = (user, age) => ({ ...user, age });
```

```js
// pure
const addOne = (num) => num + 1;

// impure: modifies input variable
const addOneImpure = (num) => num++;

// pure
const addOneToAll = (arr) => arr.map(addOne);

// impure: modifies input array
const addOneToAllImpure = (arr) => {
  for (let i = 0; i < arr.length; i++) {
    addOneImpure(arr[i]);
  }
};

// pure
const addWheels = (obj, num) => Object.assign({}, obj, { wheels: num });

const noWheelTruck = { type: "truck" };

const fourWheelTruck = addWheels(noWheelTruck, 4); // {type: 'truck', wheels: 4}
console.log(noWheelTruck); // {type: 'truck'} original object unchanged

// impure
const addWheelsImpure = (obj, num) => {
  obj["wheels"] = num;
};

const noWheelCar = { type: "car" };
const fourWheelCar = addWheelsImpure(noWheelCar, 4); // {type: 'car', wheels: 4}

console.log(noWheelCar); // { type: 'car', wheels: 4 } MUTATED!
```

> "throw": Throwing an exception is actually kind of side effect – it can lead to termination of the program.

Although the type signature tells us that divide returns a number, this is not always the case.

```js
function divide(x: number, y: nmber): number {
  if (y === 0) {
    throw new Error(`Cannot divide by zero`);
  }
  return x / y;
}
divide(1, 0);
```

---

## Iterating over Arrays: for-loop, forEach and for...of

```js
// Using for-loop
var arr = [42, 7, -1];
for (var index = 0; index < arr.length; ++index) {
  var current = arr[index];
  /* Do something with `current` */
}
```

```js
// Others prefer defining an additional `length` variable:
for (var index = 0, length = arr.length; index < length; ++index) {
  var current = arr[index];
  /* ... */
}
```

```js
// Another way i using `forEach`:
arr.forEach((current, index, inputArray) => {
  /* Do something with `current` */
});
```

```js
// Or using the for ... of:
for (let current of arr) {
  /* current will be the current element */
}
```

#### .forEach()

```js
// arrays
[1,2].forEach((current, index, inputArray) => console.log(current, index, inputArray));

1 0 [1, 2]
2 1 [1, 2]
```

#### Or using the for...of (arrays):

```js
var arr = [3, 5, 7, 9];
for (let n of arr) {
  console.log(n); // 3,5,7,9
}
```

---

## Iterating over Array indices and elements via the for..of loop

```js
// ❌ instead of 💩
var arr = ["a", "b", "c"];

arr.forEach(function (elem, index) {
  console.log("index = " + index + ", elem = " + elem);
});
```

```js
// better do
let arr = ["a", "b", "c"];

for (const [index, elem] of arr.entries()) {
  console.log(`index = ${index}, elem = ${elem}`);
}
// index = 0, elem = a
// index = 1, elem = b
// index = 2, elem = c
```

> arr.entries() returns an iterable over index-element pairs.
> The destructuring pattern [index, elem] gives us direct access to both components of each pair.

---

## creating table by templating via template literals

```js
const tmpl = (addrs) => `
   <table>
   ${addrs
     .map(
       (addr) => `
       <tr><td>${addr.first}</td></tr>
       <tr><td>${addr.last}</td></tr>
    `
     )
     .join("")}
    </table>
`;
const data = [
  { first: "<Jane>", last: "Bond" },
  { first: "Lars", last: "<Croft>" },
];

console.log(tmpl(data));
/*
<table>
  <tr><td><Jane></td></tr>
  <tr><td>Bond</td></tr>

  <tr><td>Lars</td></tr>
  <tr><td><Croft></td></tr>
</table>
*/
```

---

## Empty an array

```js
let myArray = [12, 222, 1000];

myArray.length = 0; // []
```

---

## Get the Last item from Array

```js
let array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

console.log(array.slice(-1)); // [9]
console.log(array.slice(-2)); // [8, 9]
console.log(array.slice(-3)); // [7, 8, 9]
```

---

## Remove element(s) from an array

```js
// An item
array.splice(index, 1);
```

```js
// First item
array.shift();
```

```js
// Last item
array.pop(); // this mutates
```

- TIP:
  What about delete? Try to avoid delete, causes sparse arrays

---

## mutator methods Vs non-mutator methods

### Mutating data can cause unintended side-effects. Do not use the mutator methods

```js
Array pop(), shift(), splice(), delete(), .copyWith(), .fill(), .pop(), .push(), .reverse(), .shift(), .sort(), .splice(), .unshift() Objects, arrays, and functions are mutable.
```

These methods modify the array: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype#Mutator_methods

### USE NON-mutating methods

```js
.concat(), .join(), .slice(), .toString(), etc
```

JS primitive data types (Number, String, Boolean, Undefined, and Null) are already immutable.

```js
// ❌ instead of 💩
// .pop()
const arr = [1, 2, 3, 4, 5, 6];

arr.pop(); //  [1, 2, 3, 4, 5]

// better do ✅
// [...arr].length - 1
const arr = [1, 2, 3, 4, 5, 6];

const newArr = [...arr].length - 1; //  [1, 2, 3, 4, 5]
```

```js
// ❌ instead of 💩
// splice
const fruits = ["peach", "pear", "apple", "plum"];

fruits.splice(2, 1); // removing [ 'apple' ]

// original fruits was mutated
fruits; // [ 'peach', 'pear', 'plum' ]

// better do ✅
// make a copy of [...fruits] then splice
const fruits = ["peach", "pear", "apple", "plum"];
const newFruits = [...fruits];

newFruits.splice(2, 1); // removing apple
```

---

## Remove betweeen few specific positions in an Array `no mutation`

```js
const originalArr = ["c", "xxxx", "yyyy", "zzzz", "javascript", "kotlin"];

const start = 1;
const howMany = 3;

const extractedArr = originalArr.filter((item, index) => {
  return index >= start && index < howMany + start;
});

extractedArr; // ["xxxx", "yyyy", "zzzz"]
```

---

## Avoid Null Comparisons: `!== null`

Values should be checked for what they ar" "expected to "e", not for what the" "aren't expected to "e": is expected to be an array, so you should be checking to see if it is an array.

```js
if (values !== null) {
  // avoid
}

// better do ✅
if (values instanceof Array) {
  // Preferred instance of optio
}
```

```js
// or even better
if (values) {
  // even better: !== 0, !== null and !== undefined
}
```

---

## Difference between USING `new` or NOT

Function Constructor uses the new operator:

```js
var fc = new Array();
// Creates a new execution context,
// When the execution runs it point at "this",
// If you don't return anything it WILL return this OBJECT (very important),

var f = foo();
// Creates a new execution context,
// When the execution runs it point at "this",
// If you don't return anything it is NOT going to return this OBJECT (very important)
```

```js
// test with or with out new:
function point(x, y) {
  console.log(x, y);
}
var myPoint2 = new point();
myPoint2 instanceof point; // true

function point(x, y) {
  console.log(x, y);
}
var myPoint3 = point();

myPoint3 instanceof point; // false
myPoint3 instanceof Object; // false
```

---

## Debounce (debaunss) Frequently Executed Events/Methods

Oftentimes developers will add events in anticipation of user interactions which could happen quite frequently. Think about the window's resize event or an element's omouseover event they both fire numerous times in rapid succession while they're happening. `Debouncing` will limit the number of times a function can be run within a given time frame. Here's how you'd use function debouncing.

```js
const debounce = (fn, time) => {
  let timerId;
  return function (...args) {
    const functionCall = () => fn.apply(this, args);
    clearTimeout(timerId);
    timerId = setTimeout(functionCall, time);
  };
};
```

---

## !!coercion = boolean validator: `!!`

```js
if (value) {
  value = true;
} else {
  value = false;
}
```

```js
// same as
!!value;
```

---

## Calculate operations elements elements

```js
const values = [1, 2, 3];
let sum = 0;
for (const x of values) {
  sum = sum + x;
}

// better do ✅
const values = [1, 2, 3];
const add = (x, y) => x + y;
const sum = values.reduce(add);
```

---

## Setting properties

```js
// ❌ instead of 💩
const obj = {
  one: 1,
};
obj.two = 2;

// better do ✅
const obj = {
  one: 1,
};
const newObj = {
  ...obj,
  two: 2,
};
```

---

### Modifying Arrays

```js
// ❌ instead of 💩
const values = [1, 2, 3];
values.push(4);

// better do ✅
// Do not mutate values
const values = [1, 2, 3];
const newValues = [...values, 4];
```

---

## Classes

```js
class Cat {
  constructor() {
    this.sound = "Meow";
  }

  talk() {
    return this.sound;
  }
}

const cat = new Cat();
const talk = cat.talk;
```

```js
// ❌ instead of 💩
cat.talk(); //  'Meow'
talk(); //  Error: Cannot read property 'sound' of undefined

// better do ✅
// Separation of function from data for maximum reusability
const cat = {
  sound: "Meow",
};

const dog = {
  sound: "Woof",
};

const talk = (animal) => animal.sound;

talk(cat); //  'Meow'
talk(dog); //  'Woof'
```

---

## `!== typeof` Vs `in` Vs `hasOwnProperty`

```js
if ("undefined" !== typeof obj["prop"]) {}

if ("prop" in obj) {}

if (obj.hasOwnProperty("prop")) {}
```

- LINKS:
  [=== vs in vs hasOwnProperty](http://andrew.hedges.name/experiments/in/)
  [A MB getDrink implementation](https://toddmotto.com/deprecating-the-switch-statement-for-object-literals/)

---

## pick from an object the values tht match and array. MB

Picks the key-value pairs corresponding to the given keys from an object.

```js
const pick = (obj, arr) =>
  arr.reduce((acc, curr) => (curr in obj && (acc[curr] = obj[curr]), acc), {});

pick({ a: 1, b: "2", c: 3 }, ["a", "c"]); // { 'a': 1, 'c': 3 }
```

---

## Pick / search from object values that are number. MB

Creates an object in return of the pick and the conditional

> Use Object.keys(obj) and Array.prototype.filter()to remove the keys for which fn returns a falsy value.
> Use Array.prototype.reduce() to convert the filtered keys back to an object with the corresponding key-value pairs.
> The callback function is invoked with two arguments: (value, key).

```js
const pickBy = (obj, fn) =>
  Object.keys(obj)
    .filter((k) => fn(obj[k], k))
    .reduce((acc, key) => ((acc[key] = obj[key]), acc), {});

pickBy({ a: 1, b: "2", c: 3 }, (x) => typeof x === "number"); // {'a':1, 'c':3}
```

---

## pipe Functions that abstract, pipe and reuse the logic. MB. Utility

```js
const pipeFunctions = (...fns) =>
  fns.reduce(
    (f, g) =>
      (...args) =>
        g(f(...args))
  );

const add5 = (x) => x + 5;
const multiply = (x, y) => x * y;
const multiplyAndAdd5 = pipeFunctions(multiply, add5);

multiplyAndAdd5(5, 2); // 15
```

---

## pick and pull from a given array . utility. MB

> filter / remove from array from parameters values

```js
const pull = (arr, ...args) => {
  let argState = Array.isArray(args[0]) ? args[0] : args;
  let pulled = arr.filter((v) => !argState.includes(v));
  arr.length = 0;
  pulled.forEach((v) => arr.push(v));
};

let myArray = ["A", "B", "c", "A", "B", "c"];

console.log(pull(myArray, "A", "B")); // myArray = [ 'b', 'b' ]
```

---

## filter array by primitive data types (String, Number, Boolean, undefined, and null) 

```js
const arr=["hello", false, 0, "", 7, true, "0", [] , {},null, undefined];
arr.filter(String); // ['hello', false, 0, 7, true, '0', {...}, null]

const arr=["hello", false, 0, "", 7, true, "0", [] , {},null, undefined];
arr.filter(Number); // [7, true]

const arr=["hello", false, 0, "", 7, true, "0", [] , {}, null, undefined];
arr.filter(Boolean); // ['hello', 7, true, '0', Array(0), {...}]

const arr=["hello", false, 0, "", 7, true, "0", [] , {}, null, undefined];
arr.filter(x => x === undefined); // [undefined]

const arr=["hello", false, 0, "", 7, true, "0", [] , {}, null, undefined];
arr.filter(x => x === null); // [null]
```

---

## Destructuring nested object

> Destructuring `response.body.count`: Here,first body is Destructuring,then count is destructured from body.

```js
const response = {
 msg:"success",
 body: {
    count:5,
    data:["File1","File2"],
 },
};

const {
 body : {count},
} = response;

console.log(count); // 5
```

```js
const user = {
  id: 339,
  name: 'Fred',
  age: 42,
  education: {
    degree: 'Masters'
  }
};
const {education: {degree}} = user;
console.log(degree); // Masters
```

```js
const user = {
  id: 339,
  name: 'Fred',
  age: 42
};

const {education: {school: {name}} = {}} = user;  // TypeError: Cannot match against 'undefined' or 'null'.
```

```js
const user = {
  id: 339,
  name: 'Fred',
  age: 42
};
const {education: {school: {name}} = {school: {name: 'Dunno'}}} = user;
console.log(name); // Dunno
```

---

## Custom pick for objects

```js
const pick = (obj = {},keys=[]) => {
  const result={};

  for (const key in obj){
    if (keys.includes(key)) {
      result[key] = obj[key];
    }
   } 
  return result;
}

const obj = {
  name:"Mehul",
  age:27,
  email:"codedrops.tech@gmail.com",
  website:"codedrops.tech",
};

const keys To Include=["name","age"];

console.log(pick(obj,keysToInclude)); // {name:'Mehul',age:27}
```

---

## sort and pick after a property sorted

```js
const characters = [
  { id: 1, first: "Tim", last: "Draper" },
  { id: 17, first: "Tim", last: "Boies" },
  { id: 199, first: "Tim", last: "Kemp" },
  { id: 75, first: "Tim", last: "Mosley" },
  { id: 444, first: "Tim", last: "Holmes" },
  { id: 95, first: "Donald", last: "Lucas" },
  { id: 186, first: "Larry", last: "Ellison" },
  { id: 364, first: "Channing", last: "Robertson" },
  { id: 285, first: "Charles", last: "Fleischmann" },
  { id: 33, first: "John", last: "Howard" },
];

characters.map((user) => user.id).sort((a, b) => a - b); //  [1, 17, 33, 75, 95, 186, 199, 285, 364, 444]
```

---

## Validate an array is Empty utility

```js
// Code
const isEmpty = (val: any) => val == null || !(Object.keys(val) || val).length;

isEmpty([]); // true
isEmpty({}); // true
isEmpty(""); // true
isEmpty([1, 2]); // false
isEmpty({ a: 1, b: 2 }); // false
isEmpty("text"); // false
isEmpty(123); // true - type is not considered a collection
isEmpty(true); // true - type is not considered a collection
```

---

## ways to create an Object

```js
var o1 = new Object();
var o2 = {};
var o3 = Object.create(null);
```

## ways to create an Array

```js
var a1 = new Array();
var a2 = [];
var Array.of(0,"test",null)
```

---

## Anonymous function signature

```js
const createUser = ({ userName = "Anonymous", avatar = "PepeAvatar" } = {}) => ({
  userName,
  avatar,
});

console.log(createUser({ userName: "Pepe" }), createUser());
// {userName: 'Pepe', avatar: 'PepeAvatar'} 
// {userName: 'Anonymous', avatar: 'PepeAvatar'}
```

---

## function factories

> A factory function it as a function that returns an object without using a constructor function or class.

```js
// eg1
// object representing Captain America
const avengers = [];
const captainAmerica = {
  name: "Steven Rogers",
  alias: "Captain America",
  abilities: [
    "Enhanced strength, speed, stamina, durability, agility, reflexes, senses, and mental processing via the super soldier serum",
    "Master martial artist and hand-to-hand combatant",
    "Accelerated healing",
    "Immunity to diseases and toxins",
    "Slowed aging",
    "Master tactician, strategist, and field commander",
    "Using Vibranium-steel alloy shield",
  ],
};

// That's it. That's a factory function
// factory function that will make this object for us.
const makeHero = (name, alias, abilities) => {
  const hero = {};
  hero.name = name;
  hero.alias = alias;
  hero.abilities = abilities;
  return hero;
};

// To create a new object using this factory
const captainAmerica = makeHero("Steven Rogers", "Captain America", [
  "Enhanced strength, speed, stamina, durability, agility, reflexes, senses, and mental processing via the super soldier serum",
  "Master martial artist and hand-to-hand combatant",
  "Accelerated healing",
  "Immunity to diseases and toxins",
  "Slowed aging",
  "Master tactician, strategist, and field commander",
  "Using Vibranium-steel alloy shield",
]);
```

```js
// eg2
function hello(lang) {
    return function(firstname,lastname){
    if(lang === 'en'){
      console.log('Hello ' + firstname + lastname);
    }
    if(lang === 'es'){
      console.log('Hola ' + firstname + lastname);
    }
  }
}

var en = hello('en');
var es = hello('es');

en('Leo','Lane'e'); // Hello LeoLanese
es('Leo','Lane'e'); // Hola LeoLanese
```

---

## DRY

If you are repeating yourself, you're doing it wrong (typical case is when you are C&Pasting and change just the values).
Avoid repetition specially where JS is slow.

```js
if (1 === "activate") {
  sound.play();
}
if (2 === "activate") {
  sound.play();
}
if (3 === "activate") {
  sound.play();
}
```

```js
// BETTER
// put all the properties within array
var obj = ["active", "active", "active"];

// or create an Object Literal
var myObj = {
  1: "active",
  2: "active",
  3: "active",
};

Object.keys(myObj).forEach((key) => {
  console.log(key); // the name of the current key.
  console.log(myObj[key]); // the value of the current key.
});
```

---

## Some old best practices

- What slow on JS?

* DOM manipulation
* function calls
* lookups (talk lookups)

```js
// avoid
var foo = 42;
(function () {
  (function () {
    (function () {
      alert(foo); // 3 scope lookups
    })();
  })();
})();
```

- Avoid scope-lookUps

  Specially if some slow JS process is involved, loops, intervals.

- EVENT DELEGATION:

  Something needs to happen when each child element is clicked.
  You could add a separate event listener to each individual LI element, but what if
  'LI' elements are frequently added and removed from the list?
  The better solution is to add an event listener to the UL parent element.

```js
<ul id="parent-list">
  <li id="post-1">Item 1</li>
  <li id="post-2">Item 2</li>
  <li id="post-3">Item 3</li>
  <li id="post-4">Item 4</li>
  <li id="post-5">Item 5</li>
  <li id="post-6">Item 6</li>
</ul>
```

But if you add the event listener to the parent, how will you know which element was clicked?
Simple: when the event bubbles up to the UL element, you check the event object's
target property to gain a reference to the actual clicked node:

```js
// using $
'('#parent-list').on('click',function(){
  if(e.target && e.target.nodeName == "LI") {
  // List item found! Output the ID!
  console.log("List item ",e.target.id.replace("post-")," was clicked!");
  }
})

// using JS Get the parent DIV, add click listener...
document.getElementById("parent-list").addEventListener("click",function(e) {
  // e.target was the clicked element
  console.log( e.target)
});
```

- Be careful using: parseInt()

```js
  parseInt('10'); // 10
  parseInt('010'); // 8

  We need to specified the base to use:
  parseInt('010', 10); // 10

  // Or we can use:
  Number('010'); // 10
```

- Avoid !== null comparison:

```js
// AVOID
var n !== null

// instead USE
use instanceof instead
```

- Beware Loose Types:

```js
///When doing mathematical operations, JavaScript can convert numbers to stings:
var x = 5 + 7; // x.valueOf() is 12, typeof x is a number
var x = 5 + "7"; // x.valueOf() is 57, typeof x is a string
```

---

## minify techniques

- Bundle the js: Pack all JS and CSS

- Minify JS and CSS: Remove comments & Remove duplication
- Obfuscate: Technique to reduce the name of the all variables in the code: JSON, JS, css, etc
- GZIP compression: Enable file compression using mod_gzip Apache on server side
- deflate compression': Enable file compression using mod_deflate Apache on server side
- server caching: avoiding to generate this big process on every request on server
- Client-side caching
- "Don't modify objects I don't own"

---

## Argument sanity check (validate parameters)

Functions and objects are passed as arguments to other functions without any type validation

Type validation is an essential step in ensuring that you are working only with input of a desired type. Without sanitisation checks in place, you run the risk of users passing in just about anything (a string, a date, an array, etc.),

For functions, you should do the following at a minimum:
1- Test to ensure that arguments being passed actually exist,

```js
typeof null; // Object
typeof NaN; // number
typeof Number(1) === "number"; // but never use this form!
typeof NaN == "number"; //true :(
typeof function () {} === "function"; // true

var injectToStart = function (aValue) {
  if (
    typeof aValue != "undefined" &&
    aValue !== null &&
    aValue instanceof Array &&
    typeof arr.length === "number"
  ) {
    // or simple if(aValue){}
    alert(aValue);
  } else {
    // ...
  }
};
```

Example 2:

```js
function sayHi(who) {
  who = who || ''e'; // if who is falsy, returns 'me'
  alert(who)
}
sayHi("John")
sayHi() // 'me'
```

---

### Create a better use betterTypeOf

> Be aware of typeof bug. Check to prevent the app from executing input that is not a valid function at all.

```js
var n = new Array();
typeof(n); // object :(

typeof(null); // "object"
betterTypeOf(null); // "null"

typeof([1,2]); // "object"
betterTypeOf([1,2]) // "array"

console.log(typeof null); // object? BUG :(
betterTypeOf(null); // null

var n = [];
console.log(typeof n): // Object? Not Array

var n2 = null;
console.log(typeof n2): // Object? Not null

function Person(name) {
  this.name = name;
}
var e = new Person('Jane'); // function Constructor
console.log(typeof e); // object, that fine!

// better do ✅
const betterTypeOf = (obj) =>
  ({}.toString
    .call(obj)
    .match(/\s([a-zA-Z]+)/)[1]
    .toLowerCase());

betterTypeOf(null); // null
betterTypeOf(NaN); // number
betterTypeOf({ a: 4 }); //"object"
betterTypeOf([1, 2, 3]); //"array"

(function () {
  console.log(toType(arguments));
})(); //arguments

betterTypeOf(new ReferenceError()); //"error"
betterTypeOf(new Date()); //"date"
betterTypeOf(/a-z/); //"regexp"
betterTypeOf(Math); //"math"
betterTypeOf(JSON); //"json"
betterTypeOf(new Number(4)); //"number"
betterTypeOf(new String("abc")); //"string"
betterTypeOf(new Boolean(true)); //"boolean"

// alternativly
Array.isArray([]);
```

Special version of: "for statement" pattern
We can iterate through all the members of an Object:

```js
for (var name in object) {
  if (object.hasOwnProperty(name)) {
    // within the loop,
    // name is the key of current member
    // object[name] is the current value
  }
}
```

---

## const vs Object.freeze()

```js
var n = "Pepe";
Object.freeze(n);
// const n = 9;
n = "Tony"; // CHANGED, coz need to be an Object :P
console.log(n);

var obj1 = {
  internal: {},
};
Object.freeze(obj1);
obj1.internal.a = "aValue"; // CHANGED :P coz I need to do: Object.freeze(obj1.internal);
console.log(obj1); // "{"internal":{"a":"aValue"}}"

// Object.freeze()
obj1 = {
  internal: 666,
};
Object.freeze(obj1);
obj1.internal = 1; // NOT CHANGED: Cannot assign to read only property 'internal' :)

console.log(obj1); // {internal: 666}
```

```js
(() => {
  "use strict"; // want to mute the error? remove this

  var obj1 = {
    internal: {},
  };
  Object.freeze(obj1.internal);

  obj1.internal.a = "aValue"; // NOT CHANGED: Can't add property a, object is not extensible :)
  console.log(obj1);
})();
```

---

## single return Vs multiple returns

```js
// instead
private getNewDataObject(requestBody: McRequest) {
const typesToAvoidTransformation = ['string', 'boolean', 'number'];
const typeOfRequestBody = typeof requestBody;

    if (typesToAvoidTransformation.includes(typeOfRequestBody)) {
      return requestBody;
    }

    return { ...requestBody };

}

// better do ✅
private getNewDataObject(requestBody: McRequest): McRequest {
const typesToAvoidTransformation = ['string', 'boolean', 'number'];
const typeOfRequestBody = typeof requestBody;
    return typesToAvoidTransformation.includes(typeOfRequestBody) ? requestBody : { ...requestBody };
}
```

---

## Converts

### Converts: -> Camel Case

```js
const toCamelCase = (str: string) => {
  let s = str
    .match(/[A-Z]{2,}(?=[A-Z][a-z]+[0-9]*|\b)|[A-Z]?[a-z]+[0-9]*|[A-Z]|[0-9]+/g)
    ?.map((x: string) => x.slice(0, 1).toUpperCase() + x.slice(1).toLowerCase())
    .join("");
  return s && s.slice(0, 1).toLowerCase() + s.slice(1);
};

toCamelCase("some_database_field_name"); // 'someDatabaseFieldName'
toCamelCase("Some label that needs to be camelized"); // 'someLabelThatNeedsToBeCamelized'
toCamelCase("some-javascript-property"); // 'someJavascriptProperty'
toCamelCase("some-mixed_string with spaces_underscores-and-hyphens"); // 'someMixedStringWithSpacesUnderscoresAndHyphens'
```

--

### Converts: array-like into -> array

```js
function sumArguments() {
  return Array.from(arguments).reduce((sum, num) => sum + num);
}

sumArguments(1, 2, 3); // 6
```

---

### Converts: array of string -> number

This leverages the map method of Array and, by passing Number as the parameter, for each value in the array it is going to call the constructor of Number and return the result.

```js
const numbers = ["1", "2", "-4", NaN, [1.4], 0, undefined, -1, null, Infinity];
const convertNumber = numbers.map(Number);

console.log(convertNumber); // [1, 2, -4, NaN, 1.4, 0, NaN, -1, 0, Infinity]
```

---

### Converts: Array -> Observable

> Converts each emitted item and then recollect them using toArray

```js
// ❌ instead of 💩
of({ items: [1, 2, 3] })
  .pipe(map((response) => response.items))
  .subscribe((items) => {
    this.items = items.map((item) => item * 2);
  });

// better do ✅
of({ items: [1, 2, 3] })
  .pipe(
    switchMap((response) => response.items),
    map((item) => item * 2),
    toArray()
  )
  .subscribe((items) => (this.items = items));
```

---

### Converts: string -> Array of string

```js
// ej1
const words = (str, pattern = /[^a-zA-Z-]+/) =>
  str.split(pattern).filter(Boolean);

words("I love javaScript!!"); // ["I", "love", "javaScript"]
words("python, javaScript & coffee"); // ["python", "javaScript", "coffee"]
```

```js
// ej2
// ...spread operator (...) to turn strings into Arrays:
let chars = [...("Jon" + "Doe")];
console.log(chars); // ["J", "o", "n", "D", "o", "e"]
```

### Converts: number -> letter

```js
const numberToLetter = (value: number): string =>
  String.fromCharCode(94 + value);

numberToLetter(4); // b
```

---

### Converts: snakecase string -> camelcase

```js
const snakeToCamel = (s: string): string =>
  s.toLowerCase().replace(/(_\w)/g, (w) => w.toUpperCase().substring(1));

snakeToCamel("foo_bar"); // fooBar
```

---

## Converts: `JSON -> ts` and `JSON -> Interface`

- Create Interfaces from API response:
  If you have a big, nested response from the API, it's really tedious to type the corresponding interface(s) by hand.

- LINKS:
  https://transform.now.sh/json-to-go/
  https://app.quicktype.io/
  http://www.jsontots.com/
  http://www.json2ts.com/


```js
Rx.Observable.of({
  0: { data: "lorem" },
  1: { data: "lorem" },
  2: { data: "lorem" },
})
  .map((data) => Object.keys(data).map((k) => data[k]))
  .subscribe((data) => console.log(data));
```

---

## Converts: object -> Map

```js
const obj = { foo: "bar", baz: 42 };
Object.entries(obj).forEach(([key, value]) => console.log(`${key}: ${value}`)); // "foo: bar", "baz: 42"
```

---

### Converts: object -> array

```js
const obj = { background: "#CFEBB3", color: "#000" };

Object.entries([obj]); // [Array[2]]
```

---

### Converts: string -> Array of objects

```js
let arr = [1,2,3,4,5,6,7,8,9]

const convert_obj = {...arr}; 
// {"0": 1, "1": 2, "2": 3, "3": 4, "4": 5, "5": 6, "6": 7, "7": 8, "8": 9,"9": 10}
```

```js
const str = "Option 1|false|Option 2|false|Option 3|false|Option 4|true",
  data = [];
for (let i = 0, a = str.split("|"); i < a.length; i += 2) {
  const option = a[i],
    value = JSON.parse(a[i + 1]);
  data.push({ option, value });
}

console.log(data);
// [
//   {option: "Option 1", value: false}
//   {option: "Option 2", value: false}
//   {option: "Option 3", value: false}
//   {option: "Option 4", value: true}
// ]
```

---

### Converts: Object -> array

```js
Object.entries([
  { background: "#CFEBB3", color: "#000", cursor: "blackCursor" },
  { background: "#C0E1A0", color: "#111" },
  { background: "#95CD61" },
  { background: "#85B100" },
  { background: "#FED003", color: "#000" },
]); // [Array[2], Array[2], Array[2], Array[2], Array[2]]
```

```js
const objectoToArray = (obj) => Object.keys(obj).map((n) => [n, obj[n]]);
objectoToArray({ 1: 1, 2: 2, 3: 3 }); // [["1", 1], ["2", 2], ["3", 3]]

// better do ✅
const obj = { 1: 1, 2: 2, 3: 3 };
result = Object.keys(obj).map((key) => [Number(key), obj[key]]);
```

```js
const obj = { one: "Leo", two: "Tom", three: "Sam" };

console.log(Object.entries(obj)); // [["one", 'Leo'], ["two", 'Tom'], ["three", 'Sam']]
```

---

### Converts: String -> Array

Object to Array

we have 3 types convert Object to array

1. Object.Keys : using this method, will get a all keys as an array
2. Object.values: using this method will get all values as an array
3. Object.entries: will get both key and value in array

```js
// eg1
let obj = {
    one : 'a',
    two : 'b',
    three : 'c'
};

/*1. Object.keys*/
const keys = Object.keys(obj) //['one', 'two', 'three']

/*2. Object.values*/             
const values = Object.values(obj) // ['a', 'b', 'c']

/*3. Object.entries*/
const entries = Object.entries(obj) // [ ["one", "a"], ["two", "b"], ["three","c"] ]
```


```js
// eg2
const name = "Chuloo";
const map = Array.prototype.map;

const newName = map.call(name, (eachLetter) => {
  return `${eachLetter}a`;
});

console.log(newName); // ['Ca', 'ha', 'ua', 'la', 'oa', 'oa']
```

---

### Converts: Number -> Array of Digits

```js
const convertToArray = (number) => [...`${number}`].map((el) => parseInt(el));

convertToArray(5678); // [5,6,7,8]
```

```js
Array.of(5); // [5]
Array.of(1, 2, 3); // [1, 2, 3]

Array(5); // array of 5 empty slots
Array(1, 2, 3); // [1, 2, 3]
```

---

### Converts: Object -> Array of object

The Object.entries() method returns an array of a given object's

```js
const moreAnimals = { camel: "c", boar: "b", turkey: "t" };
const entries = Object.entries(moreAnimals); // [{ camel: "c",  boar: "b",  turkey: "t"}]
```

---

### Converts: -> Boolean

```js
const isTrue = !0; // true
const alsoFalse = !!0; // false

typeof isTrue; // boolean
typeof alsoFalse; // boolean
```

---

### Converts: Number -> String

```js
const val = 5 + ""; // "5"

typeof val; // string
```

---

### Converts: String -> Number

```js
let int = "15";
int = +int; // 15

typeof int; // number
```

---

### Converts: float -> int

```js
const int = 21.4 | 0; // 21

typeof int; // "number"
```

---

### Converts: Map -> Object

```js
const map = new Map();
map.set("one", 1);
map.set("two", 2);

const obj = Object.fromEntries(map);

console.log(obj); // {one: 1, two: 2}
```

---

### Converts: string -> array

```js
const str = "hello";
const strChar = [...str];
console.log(strChar); // would display ['h', 'e',' l',' l', 'o']
```

---

### Converts: number -> array

```js
const convertNumberToArray = (num) => [...`${num}`].map((n) => parseInt(n));

convertNumberToArray(1234); // [1, 2, 3, 4]
```

---

### Converts: array -> object

```js
const arr = [
  ["1", 1],
  ["2", 2],
  ["3", 3],
];
Object.fromEntries(arr); // {1:1, 2:2, 3:3}
```

---

### Converts: Object -> JSON

```js
var obj = { name: "Martin", age: 30, country: "United States" };

// Converting JS object to JSON string
var json = JSON.stringify(obj);

console.log(json);
// Prints: {"name":"Martin","age":30,"country":"United States"}
```

** LINKS
https://transform.tools/js-object-to-json/

---

## Converts: object -> array (using rxjs)

```js
Rx.Observable.of({
  0: { data: "lorem" },
  1: { data: "lorem" },
  2: { data: "lorem" },
})
  .map((data) => Object.keys(data).map((k) => data[k]))
  .subscribe((data) => console.log(data));
```

---

### Converts: iterables -> Arrays

```js
[...new Map().set(true, "yes").set(false, "no")]; // [ true, 'yes' ], [ false, 'no' ] ]
```

---

### Converts: Set -> Array

```js
const set = new Set([11, -1, 6]);
const arr = [...set]; // [11, -1, 6]
```

---

### Converts: truthy falsy -> boolean

```js
const myVar = null;
const mySecondVar = 1;

console.log(Boolean(myVar)); // false
console.log(!!myVar); // false
console.log(Boolean(mySecondVar)); // true
console.log(!!mySecondVar); // true
```

---

### Converts: String -> character array

```js
const str = "hello";
const strChar = [...str];

console.log(strChar); // ['h', 'e',' l',' l', 'o']
```

---

### Converts: Object -> Array typescript

```js
var employees = {
  kiran: { age: 30, salary: 10000 },
  john: { age: 35, salary: 15000 },
  Tom: { age: 21, salary: 5000 },
};
let arr = [];
Object.keys(employees).map(function (key) {
  arr.push({ [key]: employees[key] });
  return arr;
});

console.log("Object=", employees); //
console.log("Array=", arr); //
```

---

### Converts: Array -> objects

```js
let myObject = {
  name: "kiran",
  age: 45,
  salary: 2000,
};
let myArray = [];
myArray.push(myObject);

console.log(myArray); // {name: "kiran", age: 45, salary: 2000}
```

---

### Converts: string -> character array

```js
const str = "hello";
const strChar = [...str];

console.log(strChar); // would display ['h', 'e',' l',' l', 'o']
```

---

### Converts: Array of Object -> Object

```js
const posts = [
  { id: 1, category: "frontend", title: "All About That Sass" },
  { id: 2, category: "backend", title: "Beam me up, Scotty: Apache Beam tips" },
  { id: 3, category: "frontend", title: "Sanitizing HTML" },
];

const categoryPosts = posts.reduce((acc, post) => {
  let { id, category } = post;
  return { ...acc, [category]: [...(acc[category] || []), id] };
}, {});
```

---

### Converts: object -> array

```js
const obj = { one: "Leo", two: "Tom", three: "Sam" };

console.log(Object.entries(obj)); // [["one", 'Leo'], ["two", 'Tom'], ["three", 'Sam']]
```

---

### Converts: Array -> Object

```js
const myArray = [
  ["one", 1],
  ["two", 2],
  ["three", 3],
];
const obj = Object.fromEntries(myArray);
console.log(obj); // {one: 1, two: 2, three: 3}
```

---

### Converts: Map -> Object:

```js
const map = new Map();
map.set("one", 1);
map.set("two", 2);

const obj = Object.fromEntries(map);

console.log(obj); // {one: 1, two: 2}
```

---

#### Converts: Array of objects -> a single object

```js
const configs = [{ serverPort: 8080 }, { loggerName: "foo-bar" }];

reducedConfig = configs.reduce((accumulator, currentValue) => ({
  ...accumulator,
  ...currentValue,
})); // {serverPort: 8080, loggerName: "foo-bar"}
```

---

### Object.assign vs Object Spread

> '...' could be used to represent either a spread operator or a rest parameter

### There's an easy way to distinguish between them:

```js
When ... is at the end of function parameters, it's "rest parameters" and
gathers the rest of the list of arguments into an array. When ... occurs in a
function call or alike, it's called a "spread operator" and expands an array
into a list.
```

> The rest parameters must be at the end

// Spread:
The fundamental idea of the object spread operator is to create a new plain object using the own
properties of an existing object.

> So {...obj} creates a new object with the same properties and values as obj

```js
const obj = { foo: "bar" };
const clone = { ...obj }; // { foo: 'bar' }
obj.foo = "baz";
clone.foo; // 'bar'
```

// Object.assign()

```js
let c = { a: 1 };
let d = Object.assign(c);
```

// INSTEAD

```js
return getAddedIds(state.cart).map((id) =>
  Object.assign({}, getProduct(state.products, id), {
    quantity: getQuantity(state.cart, id),
  })
);
```

```js
return getAddedIds(state.cart).map((id) => ({
  ...getProduct(state.products, id),
  quantity: getQuantity(state.cart, id),
}));
```

Using Using Object Spread Operator instead Object.assign()
https://redux.js.org/recipes/using-object-spread-operator

---

### How do I use JavaScript to modify the URL without reloading the page?

#### Using the History API

```js
// use either history.pushState() or history.replaceState()
// Current URL: https://my-website.com/page_a
const nextURL = "https://my-website.com/page_b";
const nextTitle = "My new page title";
const nextState = { additionalInformation: "Updated the URL with JS" };

// This will create a new entry in the browser's history, without reloading
window.history.pushState(nextState, nextTitle, nextURL);

// This will replace the current entry in the browser's history, without reloading
window.history.replaceState(nextState, nextTitle, nextURL);
```

#### Using the Location API

```js
// modify the URL, using either window.location.href, location.assign() or location.replace():
// Current URL: https://my-website.com/page_a
const nextURL = "https://my-website.com/page_b";

// This will create a new entry in the browser's history, reloading afterwards
window.location.href = nextURL;

// This will replace the current entry in the browser's history, reloading afterwards
window.location.assign(nextURL);

// This will replace the current entry in the browser's history, reloading afterwards
window.location.replace(nextURL);
```

---

### length of an object

```js
let data = { a: 1 };

Object.keys(data).length; // 1
```

---

### use concat instead push

```js
// ❌ instead of 💩
var arr1 = ["a", "b", "c"];
var arr2 = ["d", "e", "f"];
var arr3 = arr1.push(arr2);

console.log(arr3); // 4
console.log(arr1); // ["a", "b", "c", ["d", "e", "f"]]

// better do ✅
var arr1 = ["a", "b", "c"];
var arr2 = ["d", "e", "f"];
var arr3 = arr1.concat(arr2);

console.log(arr3); // ["a", "b", "c", "d", "e", "f"]
```

---

### copy to the clipboard in JavaScript

```js
<p className="deposit-copy-this-label">
  TO BE COPY!
</p>
<div id="copy-this">
  <p>{this.dataResponse?.value?.destinationWallet}</p>
</div>


  copyToClipboard() {
    const textToCopy = document.getElementById('copy-this').innerText

    if (navigator.clipboard) {
      navigator.clipboard
        .writeText(textToCopy)
        .then(() => {
          console.log('Text copied to clipboard')
        })
        .catch((err) => {
          console.error('Error copying text: ', err)
        })
    } else {
      // Fallback legacy browsers
      const textArea = document.createElement('textarea')
      textArea.value = textToCopy
      document.body.appendChild(textArea)
      textArea.focus()
      textArea.select()
      try {
        document.execCommand('copy')
        console.log('Text copied to clipboard')
      } catch (err) {
        console.error('Error copying text: ', err)
      }
      document.body.removeChild(textArea)
    }
  }
```

---

### Object.assign

```js
// ❌ instead of 💩
options = Object.assign({}, optionsDefault, options);

const x1 = (x) => Object.assign({}, x, { val: x.val + 1 });

// better do ✅: Object spread
options = { ...optionsDefault, ...options };

const x1 = (x = { x, ...{ val: x.val + 1 } });
```

---

### Spread operator Immutable object update

```js
const book = {
  name: "JavaScript: The Definitive Guide",
  author: "David Flanagan",
  edition: 5,
  year: 2008,
};

const newerBook = {
  ...book,
  edition: 6, // <--Overwrites book.edition
  year: 2011, // <--Overwrites book.year
};

console.log(newerBook);
/*
{
  name: 'JavaScript: The Definitive Guide',
  author: 'David Flanagan',
  edition: 6,
  year: 2011
}
*/
```

---

### filter object

```js
import { from, of } from "rxjs";
import { pluck } from "rxjs/operators";

const source = of({
  name: "Joe",
  age: 30,
});
//grab names
const example = source.pipe(pluck("name"));
//output: "Joe", "Sarah"
const subscribe = example.subscribe((val) => console.log(val));
```

## https://stackblitz.com/edit/typescript-b68qdv?file=index.ts

---

### trimStart() and trimEnd()

```js
const str = "   string   ";

// es2019
console.log(str.trimStart()); //  "string   "
console.log(str.trimEnd()); //  "   string"

// the same as
console.log(str.trimLeft()); //  "string   "
console.log(str.trimRight()); // "   string"
```

---

### flat() and flatMap()

> flat() method enables you to easily concatenate all sub-array elements of an array

```js
const arr = ["a", "b", ["c", "d"]];
const flattened = arr.flat();
console.log(flattened); //  ["a", "b", "c", "d"]
```

```js
const arr = ["a", , , "b", ["c", "d"]];
const flattened = arr.flat();

console.log(flattened); // ["a", "b", "c", "d"]
```

```js
const arr = [4.25, 19.99, 25.5];

console.log(arr.map((value) => [Math.round(value)])); // [[4], [20], [26]]
console.log(arr.flatMap((value) => [Math.round(value)])); // [4, 20, 26]
```

---

### do not include items bigger than 9

```js
const arr = [[7.1], [8.1], [9.1], [10.1], [11.1]];

arr.flatMap((value) => Math.round(value)); // [7, 8, 9, 10, 11]
```

---

### Copy part of array with and returns modified array: Array.copyWithin()

> `arr.copyWithin(target, start, end)`: copyWithin() method copies the part of the given array with its elements and returns the modified array.

```js
The copyWithin() method takes in: target - The index position to copy the
elements to. start (optional) - The index position to start copying elements
from. If omitted, it will copy from index 0. end (optional) - The index position
to end copying elements from. (exclusive) If omitted, it will copy until last
index.
```

```js
let shows = [
  "Pink Panther",
  "Chhota Bheem",
  "Oggy",
  "Tom and Jerry",
  "Doraemon",
];

shows.copyWithin(2, 0, 2); // ["Pink Panther", "Chhota Bheem", "Pink Panther", "Chhota Bheem", "Doraemon"]

[21, 19, 46, 4, 5].copyWithin(-2); // [21, 19, 46, 21, 19]
[21, 19, 46, 4, 5].copyWithin(0, 3); // [4, 5, 46, 4, 5]
[21, 19, 46, 4, 5].copyWithin(0, 3, 4); // [4, 19, 46, 4, 5]

[1, 2, 3].copyWithin(1); // [1, 1, 2]
[1, 2, 3].copyWithin(2); // [1, 2, 1]
[1, 2, 3].copyWithin(3); // [1, 2, 3]
```

```js
let array = [1, 2, 3, 4, 5, 6];

// target: from second-to-last element, start: 0, end: array.length
let returned_arr = array.copyWithin(-2);
console.log(returned_arr); // [ 1, 2, 3, 4, 1, 2 ]
// modifies the original array
console.log(array); // [ 1, 2, 3, 4, 1, 2 ]

array = [1, 2, 3, 4, 5, 6];
// target: 0, start copying from 5th element
array.copyWithin(0, 4);
console.log(array); // [ 5, 6, 3, 4, 5, 6 ]

array = [1, 2, 3, 4, 5, 6];
// target: 1, start copying from 3rd element to second-to-last element
array.copyWithin(1, 2, -1); // -1 = last element (exclusive)
console.log(array); // [ 1, 3, 4, 5, 5, 6 ]
```

---

### upercase toLocaleUpperCase()

```js
let data = "brōkən";

console.log(data.toLocaleUpperCase("en-US")); // BRŌKƏN
```

---

### Importing JSON Files via Static import Declarations

```js
// tsconfig.json
{
"compilerOptions": {
  "target": "es2015",
  "module": "commonjs",
  "strict": true,
  "moduleResolution": "node",
  "resolveJsonModule": true
  }
}
```

```js
import * as express from "express";
import * as config from "./config.json";

const app = express();

app.listen(config.server.nodePort, () => {
  console.log(`Listening on port ${config.server.nodePort} ...`);
});
```

---

#### `FUNCTIONS` VS. `METHODS` IN JAVASCRIPT

Simply put, a `Function is a piece of code that can be called by its name`. It can be pass arguments and return values.
However, `Methods is a piece of code that must be called by its name along with its associated object name`.

### Function

// A Simple Function

```js
var simple = (a) => {
  return a;
}; // A simple function
simple(5); //called by its name
```

### Method

// A Simple Method

```js
var obj = {
  simple: (a) => {
    return a;
  },
};
obj.simple(5); //called by its name along with its associated object
```

---

### remove duplicate elements from array javascript

```js
const numbers = [2, 3, 4, 4, 2, 3, 3, 4, 4, 5, 5, 6, 6, 7, 5, 32];

console.log([...new Set(numbers)]); // [2, 3, 4, 5, 6, 7, 32]
```

---

### validate !== null and object

// DONT DO: typeof bar === "object"
// null is also considered an object so

```js
// ❌ instead of 💩
var bar = null;
console.log(typeof bar === "object"); // logs true! -> null object?

// better do ✅
var bar = null;
console.log(bar !== null && bar.constructor === Object); // logs false
```

---

### What's the difference between `setTimeout()` and `setInterval()`?

#### Definitions:

- `setTimeout()` allows to run a function once after the interval of time.<br>
- `setInterval()` allows to run a function regularly with the interval between the runs.<br>

#### Running regularly:

One is setInterval(), the other one is a "recursive setTimeout()"

#### Recursive setTimeout

```js
let timerId = setTimeout(tick() => {
  alert('tick');
  timerId = setTimeout(tick, 2000); // (*
}, 2000);
```

> I can't even begin to tell you how many "JavaScript developers" I've interviewed who cannot answer this. I'm floored every time!

```js
- setInterval() code executes every 1000ms exactly, while the setTimeout() waits
1000ms, runs the function (which takes some ms), then sets another timeout after. So,
the wait period is actually greater than 1000ms. 

setInterval() execute infinite times after the interval - setTimeout() execute one after the ms time
```

---

### Functions Rest Parameters: return (...args)

The rest parameter syntax allows us to represent an 'indefinite number of arguments as an array.'

```js
function sum(...args) {
  return args.reduce((previous, current) => {
    return previous + current;
  });
}
console.log(sum(1, 2, 3)); // 6
console.log(sum(1, 2, 3, 4)); // 10

function myFun(a, b, ...manyMoreArgs) {
  console.log(a, b, manyMoreArgs);
}
myFun("one", "two", "three", "four", "five", "six"); // "one" "two" Array ["three", "four", "five", "six"]
```

---
## Functions must return a unique data type

// 1 is integer = "Error" is string

```js
foo () => {
    ( 1 == 1 )? 1: "error";
}
```

---

## Immutable merge arrays

```js
const a = [1, 2, 3];
const b = [4, 5, 6];

console.log([...a, ...b]); // [1, 2, 3, 4, 5, 6]
```

```js
// good on very large arrays
const a = [1, 2, 3];
const b = [4, 5, 6];
a.push.apply(a, b);

a; // [1, 2, 3, 4, 5, 6]
```

### clone and merge using `...spread` / making a copy

```js
var obj1 = { foo: "bar", x: 42 };
var obj2 = { foo: "baz", y: 13 };
var clonedObj = { ...obj1 }; // { foo: "bar", x: 42 }
var mergedObj = { ...obj1, ...obj2 }; // { foo: "baz", x: 42, y: 13 }
```

### merge objects using ... rest

```js
const part1 = {
  color: "white",
};
const part2 = {
  model: "Honda",
};
const part3 = {
  year: 2005,
};

const car = {
  ...part1,
  ...part2,
  ...part3,
};
console.log(car); // { color: 'white', model: 'Honda', year: 2005 }
```

### spread modify objects

```js
const box = {
  color: "red",
  size: {
    width: 200,
    height: 100,
  },
  items: ["pencil", "notebook"],
};

const biggerBox = {
  ...box,
  size: {
    ...box.size,
    height: 200,
  },
};

console.log(biggerBox);
/*
{
  color: 'red',
  size: {
    width: 200,
    height: 200 <--Updated value
  },
  items: ['pencil', 'notebook']
}
*/
```

```js
const blackBox = {
  ...box,
  color: "black",
  size: {
    ...box.size,
    width: 400,
  },
  items: [...box.items, "ruler"],
};
console.log(blackBox);
/*
{
  color: 'black', <--Updated value
  size: {
    width: 400, <--Updated value
    height: 100
  },
  items: ['pencil', 'notebook', 'ruler'] <--A new item ruler
}
*/
```

---

### display partial Object rest properties

```js
const style = {
  width: 300,
  marginLeft: 10,
  marginRight: 30,
};

const { width, ...margin } = style;

console.log(width); // 300
console.log(margin); // { marginLeft: 10, marginRight: 30 }
```

---

### get max value from Array

```js
let arr = [-1, 7, 2, null, -0, +0, 10];
let highest = Math.max(...arr); // 10
```

---

### Returns the min / maxi value of an array

Returns the minimum/maximum value of an array, after applying the provided function to set comparing rule.

```js
const reduceWhich = <T extends number | string | AnyObject = number>(
  arr: T[],
  comparator: Function = (a: number, b: number) => (a - b) as number
) => arr.reduce((a: T, b: T) => (comparator(a, b) >= 0 ? b : a));


reduceWhich([1, 3, 2]); // 1
reduceWhich([1, 3, 2], (a, b) => b - a); // 3
reduceWhich([
    { name: "Tom", age: 12 },
    { name: "Jack", age: 18 },
    { name: "Lucy", age: 9 },
  ],
  (a, b) => a.age - b.age
); // {name: "Lucy", age: 9}
```

---
### detectDeviceType. Hack

```js
const detectDeviceType = () =>
  /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
    navigator.userAgent
  )
    ? "Mobile"
    : "Desktop";

detectDeviceType(); // "Mobile" or "Desktop"
```

---

### Shallow Copies of Objects

> Shallow Copies of Objects (ngrx issue: readonly fixed). BUT mutating the array will impact both todos

```js
const shallow = {
  text: "Water the flowers",
  completed: false,
  tags: ["garden"],
};
const shallowCopy = { ...shallow }; // ok :)

// BUT mutating the array will impact both todos
shallowCopy.tags.push("MUTATING WITH PUSH"); // tags: ["garden", "weekend"]
```

---

### Adding Properties to an Object

```js
const user = { id: 100, name: "Moon" };
const userWithPass = { ...user, password: "Password!" };

user; // { id: 100, name: 'Moon' }
userWithPass; // { id: 100, name: 'Moon', password: 'Password!' }
```

---

### Compare 2 Objects: simple and deep comparison

#### simple comparison

```js
JSON.stringify(n) === JSON.stringify(n2); // doesn't compare the inner properties
```

#### deep comparison

```js
// Lodash
_.isEqual(value, other) Performs a deep comparison between two values to determine if they are equivalent.
```

### deep comparison no lodash

Performs a deep comparison between two values to determine if they are equivalent.

```js
const equals = (a, b) => {
  if (a === b) return true;
  if (a instanceof Date && b instanceof Date)
    return a.getTime() === b.getTime();
  if (!a || !b || (typeof a !== "object" && typeof b !== "object"))
    return a === b;
  if (a.prototype !== b.prototype) return false;
  let keys = Object.keys(a);
  if (keys.length !== Object.keys(b).length) return false;
  return keys.every((k) => equals(a[k], b[k]));
};

equals(
  { a: [2, { e: 3 }], b: [4], c: "foo" },
  { a: [2, { e: 3 }], b: [4], c: "foo" }
); // true
equals([1, 2, 3], { 0: 1, 1: 2, 2: 3 }); // true

// equals(1, "1");// compile error
deepEquals(1, "1"); //false// no compile error
```

```js
function objectEquals(x, y) {
  "use strict";

  if (x === null || x === undefined || y === null || y === undefined) {
    return x === y;
  }
  // after this just checking type of one would be enough
  if (x.constructor !== y.constructor) {
    return false;
  }
  // if they are functions, they should exactly refer to same one (because of closures)
  if (x instanceof Function) {
    return x === y;
  }
  // if they are regexps, they should exactly refer to same one (it is hard to better equality check on current ES)
  if (x instanceof RegExp) {
    return x === y;
  }
  if (x === y || x.valueOf() === y.valueOf()) {
    return true;
  }
  if (Array.isArray(x) && x.length !== y.length) {
    return false;
  }

  // if they are dates, they must had equal valueOf
  if (x instanceof Date) {
    return false;
  }

  // if they are strictly equal, they both need to be object at least
  if (!(x instanceof Object)) {
    return false;
  }
  if (!(y instanceof Object)) {
    return false;
  }

  // recursive object equality check
  var p = Object.keys(x);
  return (
    Object.keys(y).every(function (i) {
      return p.indexOf(i) !== -1;
    }) &&
    p.every(function (i) {
      return objectEquals(x[i], y[i]);
    })
  );
}
objectEquals(
  { prop1: [2, { e: 3 }], prop2: [4], prop3: "foo" },
  { prop1: [2, { e: 3 }], prop2: [4], prop3: "foo" }
); // true
```

---

### clone and merge using destructoring

```js
var obj1 = { foo: "bar", x: 42 };
var obj2 = { foo: "baz", y: 13 };

var clonedObj = { ...obj1 };
// Object { foo: "bar", x: 42 }

var mergedObj = { ...obj1, ...obj2 };
// Object { foo: "baz", x: 42, y: 13 }
```

---

### Renaming Properties

```js
const renamed = ({ ID, ...object }) => ({ id: ID, ...object });
const user = {
  ID: 500,
  name: "Bob Fossil",
};
renamed(user); //  { id: 5000, name: 'Bob Fossil' }
```

---

## Converts: Strings -> Arrays

```js
let chars = [...("Jon" + "Doe")];
console.log(chars); // ["J", "o", "n", "D", "o", "e"]
```

---

### FP methods: passing F() as arguments, passing multiple params

```js
function add(x, y) {
  return x + y;
}
function subtract(x, y) {
  return x - y;
}
function callFuncWith2Arguments(arg1, arg2, func) {
  return func(arg1, arg2);
}

callFuncWith2Arguments(1, 2, add); // 3
callFuncWith2Arguments(3, 1, subtract); // 2
```

---

### validate if object. isObject. Utility

```js
function isObject(obj) {
  return (typeof obj === "object" && obj !== null) || typeof obj === "function";
}

// test
function sumArguments() {
  return Array.from(arguments).reduce((sum, num) => sum + num);
}

isObject(sumArguments); //  true
```

---

### regExp / regex calculation, search, descarting from array

#### Negative/negating lookaheads

```js
const people = `
- Bob (vegetarian)
- Billa (vegan)
- Francis
- Elli (vegetarian)
- Fred (vegan)
`;
const regex = /-\s(\w+)\s(?!\(vegan\))/g;
// |---| |-----------|
// / \
// more than one \
// word character negative lookahead
// but as few as => not followed by "(vegan)"
// possible
let result = regex.exec(people);
while (result) {
  console.log(result[1]);
  result = regex.exec(people);
}
// Result:
// Bob
// Francis
// Elli
```

---

#### positive lookaheads matching

```js
const people = `
- (vegetarian) Bob
- (vegan) Billa
- Francis
- (vegetarian) Elli
- (vegan) Fred
  `;
const regex = /(?<=\(vegan\))\s(\w+)/g;

let result = regex.exec(people);
while (result) {
  console.log(result[1]);
  result = regex.exec(people);
} // Billa, Fred
```

---

### Removing Comments from array

```js
str = str.replace(/(<!\-\-([^\-]|(\-+[^>]))*-+>)/gm, "");

// Using Replacement Callbacks
isocode = "EN-us";
isocode = isocode.replace(
  /^([a-z]+)(\-[a-z]+)?$/i,
  function (match, lang, country) {
    return lang.toLowerCase() + (country ? country.toUpperCase() : "");
  }
); // "en-us" would become "en-US"

// strip numbers from string
var someString = "Hello 123 World!";
newString = someString.replace(/[0-9]/g, "");

// strip HTML tags from array
OriginalString = "<p>test</p>";
var StrippedString = OriginalString.replace(/(<([^>]+)>)/gi, "");

// Strip Whitespace From String
var str = " a b c d e f g ";
newStr = str.replace(/\s+/g, "");
```

---

### extend and ovewrites the initial array of object

```js
extendingDateRangePickerDefaultConfig: CustomRangeDateRangePicker = {
  dateRanges: [{ id: "CUSTOM", label: "CUSTOM RANGE" }],
};

customDateRangePickerConfig: DateRangePickerConfig = Object.assign(
  {},
  dateRangePickerDefaultConfig,
  this.extendingDateRangePickerDefaultConfig
);
```

---


### Fill/populate an array with new objects

> When every item of the initialized array should be a new object, `Array.from()` is a better solution:

```js
const length = 3;
const resultA = Array.from({ length }, () => ({}));
const resultB = Array(length).fill({});

resultA; //  [{}, {}, {}]
resultB; //  [{}, {}, {}]

resultA[0] === resultA[1]; //  false
resultB[0] === resultB[1]; //  true
```

---

### Unique items of an array

```js
function unique(array) {
  return Array.from(new Set(array));
}

unique([1, 1, 2, 3, 3]); //  [1, 2, 3]
```

---

### Converts: Array-like -> array

```js
function sumArguments() {
  return Array.from(arguments).reduce((sum, num) => sum + num);
}

sumArguments(1, 2, 3); //  6
```

---

### Create a clone of the array, including all the nested ones

```js
const numbers = [
  [0, 1, 2],
  ["one", "two", "three"],
];
otherNumbers = [...numbers];
numbers[0] === otherNumbers[0]; // true
```

---

### Clone an array

Array.from(numbers) creates a shallow copy of numbers array.

```js
const numbers = [3, 6, 9];
const numbersCopy = Array.from(numbers);

numbers === numbersCopy; // false
```

---

### Redux: AVOID MUTATION

```js
// Adding an item:
// having this array of object
let arr = [
  { a: 1, b: 2 },
  { a: 3, b: 4 },
  { a: 5, b: 6 },
];
```

Instead of the push() method, we use the concat() method to add an item to an array,
because the push() method mutates the original array, whereas concat() returns a new
array:

```js
// and arr still the same SO no mutation here
target = arr.concat({ a: 7, b: 8 });
```

```js
//Removing an item:
// We use the filter() method to create a new array that excludes the given item:
// filter all items in the source except the one with the given id (a is the id/key)
n = arr.filter((x) => x.a !== 1); // {'a':3,'b':4}, {'a':5,'b':6}
```

```js
// Updating an item:
// first we need to find the position of this item in the array
index = arr.findIndex((x) => x.a === 3); // 1
beforeItems = arr.slice(0, index);
afterItems = arr.slice(index + 1);
newArr = [...beforeItems, { a: 666, b: 666 }, ...afterItems];
```

```js
// Even better
[...arr.slice(0, index), { x: 666 }, ...arr.slice(index + 1, arr.length)];
```

---

### Async / Await

```js
// promise
doAsyncFunction()
  .then((result) => doSecondAsyncFunction(result))
  .then((resultTwo) => doThirdAsyncFunction(resultTwo))
  // and so on...
  .catch(catchError);

// using async/await
// wait will pause code execution until its promise is resolved
// await may only be used inside an async function designated by that keyword,
// and the async function itself is asynchronous and will not block surrounding code.
(async function () {
  try {
    const result = await doAsyncFunction();
    const resultTwo = await doSecondAsyncFunction(result);
    const resultThree = await doThirdAsyncFunction(resultTwo);
    return resultThree;
  } catch (error) {
    catchError(error);
  }
})();
```

---

### async/await function:

```js
function logFetch(url) {
  return fetch(url)
    .then((response) => response.text())
    .then((text) => {
      console.log(text);
    })
    .catch((err) => {
      console.error("fetch failed", err);
    });
}

// And here's the same thing using async functions: It's the same number of lines, but all the callbacks are gone.
async function logFetch(url) {
  try {
    const response = await fetch(url); // await operator wait for a Promise returned by an async function
    console.log(await response.text());
  } catch (err) {
    console.log("fetch failed", err);
  }
}
logFetch(""); // page :)
```

---

### Expand elements of an array in specific places with Spread Operator (...)

```js
// ❌ instead of 💩
function myFunctions(x, y, z) {
  console.log(x);
  console.log(y);
  console.log(z);
}
var args = [0, 1, 2];
myFunctions(args);
```

```js
// better
function myFunctions(x, y, z) {
  console.log(x);
  console.log(y);
  console.log(z);
}
myFunctions(...args);
```

```js
// ❌ instead of 💩
// spread operator tip
const newObj = {
  attr_1: attr1,
  attr_2: attr2,
};

if (condition1) {
  newObj["attr_3"] = attr3;
}

// better do ✅
const newObj = {
  attr_1: "1",
  attr_2: "2",
  ...(1 === 1 ? { attr_3: "3" } : {}),
};
```

```js
// remove repeated elements from array
const uniqueArr = (arr) => [...new Set(arr)];
uniqueArr([1, 2, 2, 2, 3, 4, 4, 5, 6, 7, 7]); // [1, 2, 3, 4, 5, 6, 7]
```

```js
// Using Math Functions operation convination
let arr = [-1, 7, 2, null, -0, +0, 10];
highest = Math.max(...arr); // 10

let numbers = [9, 4, 7, 1];
Math.min(...numbers); // 1
```

```js
// spread as parameters:
function restParameters(param, ...params) {
  return params;
}
console.log(restParameters("a", "b", "c")); // ['b', 'c']
```

```js
// to turn strings into Arrays:
let chars = [...("Jon" + "Doe")];
console.log(chars); // ["J", "o", "n", "D", "o", "e"]
```

```js
// Inject elements of an array within another array:
let values = [1, 2, 4];
let some = [...values, 8]; // [1, 2, 4, 8]
let more = [...values, 8, ...values]; // [1, 2, 4, 8, 1, 2, 4]
```

```js
// calling functions with arguments:
let values = [1, 2, 4];
doSomething(...values);
function doSomething(x, y, z) {
  // x = 1, y = 2, z = 4
}
```

```js
// concatenate
var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
arr1 = [...arr1, ...arr2];
```

```js
// Spread in object literals
// It copies own enumerable properties from a provided object onto a new object.
var obj1 = { foo: "bar", x: 42 };
var obj2 = { foo: "baz", y: 13 };

var clonedObj = { ...obj1 };
// Object { foo: "bar", x: 42 }

var mergedObj = { ...obj1, ...obj2 };
// Object { foo: "baz", x: 42, y: 13 }

// Object spread
// simply add a property to an object without mutating the original:
const point2d = { x: 1, y: 2 };
const point3D = { ...point2d, z: 3 }; // {x: 1, y: 2, z: 3}

// simple shallow extend
const foo = { a: 1, b: 2 };
const bar = { c: 1, d: 2 };
/* Merge foo and bar */
const fooBar = { ...foo, ...bar };
```

---

### Lambda notation

```js
function(num) {
  return Math.pow(num, 2);
}
num => Math.pow(num, 2)
```

```js
// Lambda notation
var square = function (x) {
  return x _ x;
}
var square = x => x _ x;
```

```js
// Higher order Functions (HoF)
let numbers = [9, 4, 7, 1];
numbers.map((x) => x + 1); // [10, 5, 8, 2]
```

```js
// FP
var isBiggerThan10 = function isBiggerThan10(numb) {
  return numb > 10;
};
const isBiggerThan10 = (numb) => numb > 10;
```

```js
// IIFE
function n() {
  return "icon-error";
}
var n3 = (function () {
  return n();
})();

function n() {
  return "icon-error";
}
var n3 = (() => n())();
```

---

## Make function argument required

```js
function required(argName = 'param') {
  throw new Error(`"${argName}" is required`)
}

function iHaveRequiredOptions(arg1 = required('arg1'), arg2 = 10) {
  console.log(arg1, arg2)
}

iHaveRequiredOptions(); // throws "arg1" is required
iHaveRequiredOptions(12); // prints 12, 10
iHaveRequiredOptions(12, 24); // prints 12, 24
iHaveRequiredOptions(undefined, 24); // throws "arg1" is required
```

---

### count number of repeated 0 inside string

```js
("[0,1,0,3,4,0];".match(/[0-0]/g) || []).length; // 3
```

---

### angular use Subject instead eventEmitter and next instead emit

```js
import { Subject } from 'rxjs';

Use .Subject() instead .evetEmitter()
Use .next() instead .emit()
```

---

### Spread operator (ES6)

> Spread uses the same notation as rest: '...' What it does is quite different.
> Using object spread, you can merge both objects into a single new object (from left to right)

#### Do not use concat, better to combine multiple arrays using Spread

```js
// instead
let a = [1, 2, 3];
let b = [4, 5, 6];
// old way
let sum = a.concat(b, 7); //[1, 2, 3, 4, 5, 6, 7]

// better do ✅
// better to combine multiple arrays using Spread
let sum2 = [...a, ...b, 7];
```

#### Spread operator (can copy arrays)

```js
var array = [1, 2, 3, 4, 5];
[head, ...tail] = array;
console.log(head, tail); // 1, [2,3,4,5]
var maxValue = Math.max(...array);
console.log(maxValue); // 5
```

#### Math floor

```js
Math.floor(5.95); // 5
0 | 5.95; // 5
```

#### Eliminate duplicates from an Array

```js
const arr = [7, 3, 1, 3, 3, 7];
[...new Set(arr)]; // [ 7, 3, 1 ]
```

#### with Math functions: getting the min

```js
var numbers = [9, 4, 7, 2];
Math.min(...numbers); // 2
```

### Dynamic assigment

```js
// es5
var foo = "test"; // dynamic
var o = {};
o[foo] = 42;

// better es6
var foo = "test";
var o = {
  [foo]: 42,
};
```

---

## window object is a circular object

```js
window.window.window;
//  Window {...}

// Create an object
var foo = {};

// Point a key value to the object itself
foo.bar = foo;

// The `foo` object just became a circular one:
foo.bar.bar.bar.bar;
```

---

### .push()

```js
var obj = {
  length: 0,

  addElem: function addElem(elem) {
    // obj.length is automatically incremented every time an element is added.
    [].push.call(this, elem);
  },
};

// Let's add some empty objects just to illustrate.
obj.addElem({});
obj.addElem({});
console.log(obj.length);
```

---

## First class and higher-order functions:

```js
// higher-order
var funcAsValue = function(y) {
  return y _ 4;
};
// higher-order
var returnFunc = function(z) {
  return function(a) {
    return a _ z;
  };
};
// First class
var funcAsArgument = function(a, func) {
  return func(a);
};
```

## recursion

> Recursion (use it instead for or while loops). A recursive function is a function that quite simply calls itself

```js
// ej1
function loop(i) {
  console.log("i is " + i);
  if (i < 10) {
    loop(i + 1);
  }
}

loop(0);
```

```js
// ej2
var recursive = function (n) {
  if (n < 1) {
    return n;
  } else {
    return recursive(n - 1);
  }
};
```

```js
// ej3
// So instead using loops:
var factorial = function (n) {
  var result = 1;
  for (var x = 1; x <= n; x += 1) {
    result = x * result;
  }
  return result;
};

factorial(5); // 120
```

```js
// Ej 4)
// A stateless approach would be:
var recursiveFactorial = function (n) {
  if (n < 2) {
    return n;
  } else {
    return n * recursiveFactorial(n - 1);
  }
};

recursiveFactorial(5); // 120
```

```js
/// Ej 5) counter example:
var counter = 10;
while (counter > 0) {
  console.log(counter--);
}
```

```js
// usign recursion countdown:
var countdown = function countdown(a) {
  if (a === 0) return;
    console.log(a)
    countdown(a - 1); // recursive call
  }
};

countdown(10);
```

---

### Currying:

Since Javascript has higher-order functions we can call functions with some of its arguments pre-filled

```js
var bindExample = function (a, b) {
  return a / b;
};
var test = bindExample.bind(null, 3);

// Here test creates a new function which when invoked already has the a argument filled in as 3, then will be: 3 / 4
test(4); // 0.75
```

---

### Memoisation:

Functions that are expensive to run can be optimised with memoisation. This involves using a closure to cache the results of previous calls to the function

```js
var memoise = function (func) {
  var cache = {};
  return function (arg) {
    if (arg in cache) {
      console.log(arg + " in cache");
      return cache[arg];
    } else {
      console.log(arg + "not in cache");
      return (cache[arg] = func(arg));
    }
  };
};
```

```js
var memo = memoise(function (n) {
  return n * 2;
});

console.time("not in cache");
memo(1); // 2 (1 not in cache)
console.timeEnd("not in cache");
console.time("cache");
memo(1); // 2 (1 in cache)
console.timeEnd("cache");
```

---

### Thunks and trampolines:

A thunk is much like a continuation except that it is stored as a data structure for use at a
later time. A trampoline manages the execution and return values of thunks
(so called because it bounces thunks around).
In Javascript we can represent a thunk as follows:

```js
var thunk = function (f, lst) {
  return { tag: "thunk", func: f, args: lst };
};

var thunkValue = function (x) {
  return { tag: "value", val: x };
};
```

Passing Functions as Parameters to Another Function:
We have established that a function can be stored in (actually, assigned to) a variable,
these variables can be passed as parameters to another function. So, instead of executing the
function and passing the result as a parameter to the function, the entire function declaration
can be passed as a parameter.

### (!) Summary:

A function is just a declaration until it is explicitly evaluated.
The declaration can be assigned to a variable, which can then be passed as a parameter to another
function.

So, a JavaScript Function is a JavaScript Variable until it is executed (evaluated).

---

### Testing for Undefined Variables

```js
typeof foo !== "undefined";
```

// check whether SomeImportantThing has been initialised

```js
if (!SomeImportantThing) {
  // FAIL
  var SomeImportantThing = {};
}
```

```js
var SomeImportantThing;
// make sure it's there
if (!SomeImportantThing) {
  SomeImportantThing = {};
}
```

---

## Deleting object Properties

```js
undefined or null only removes the value associated with the property, but not the key.
```

```js
var obj = {
  bar: 1,
  foo: 2,
  baz: 3,
};
obj.bar = undefined;
obj.foo = null;
delete obj.baz;

for (var i in obj) {
  if (obj.hasOwnProperty(i)) {
    console.log(i, "" + obj[i]);
  }
}
```

---

### hasOwnProperty

```js
var foo = {};
foo.bar = "10";

foo.hasOwnProperty("bar"); // true
```

```js
var foo = {
  bar: "Here be dragons",
};
foo.hasOwnProperty("bar"); // true
```

---

### console.table()

```js
function Person(firstName, lastName, age) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.age = age;
}

var family = {};
family.mother = new Person("Susan", "Doyle", 32);
family.father = new Person("John", "Doyle", 33);
family.daughter = new Person("Lily", "Doyle", 5);
family.son = new Person("Mike", "Doyle", 8);

console.table(family, ["firstName", "lastName", "age"]);
```

---

# console.log colors

```js
console.log(
  "%cAlert Dialog Service: %cErrorCallback: Error sign in credential",
  "color: blue;",
  "color: red;"
);
```

---

### IIFE: Immediately Invoked Function Expression.

### benefits:

- you shouldn't end up writing any kind of global variables
- You can pass parameters into it.

```js
(function (angular) {
  // your code goes here
})(window.angular);
```

```js
// evaluate the function inside the parentheses
(function () {})(); // and return the function object // call the result of the evaluation
```

```js
// A few other styles for directly invoking the
!(function () {})() + (function () {})()((function () {})());
// and so on...
```

---

### Block-Scoped Declarations pattern IIFE:

If you needed to create a block of scope, the most prevalent way to do so was the IIFE

```js
var a = 2;
(function () {
  var a = 3;
  console.log(a); // 3
})();
console.log(a); // 2
```

// If I want to pass something to the IIFE blocked scope

```js
var a = 2;
(function (b) {
  var a = 3;
  console.log(a); // 3
  console.log(b);
})("Leo"); // function that envoque
console.log(a); // 2
```

---

## Default Parameter Values

```js
// ❌ instead of 💩
function foo(x, y) {
  x = x || 11;
  y = y || 31;
  console.log(x + y);
}

foo(); // 42
foo(5, 6); // 11
foo(5); // 36
foo(null, 6); // 17Th

// better do ✅
var doWork = function (name = "Leo") {
  return name;
};
```

---

### Rest

```js
const fn = (...args) => console.log(args);

fn(1, 2, 3); //[1, 2, 3]
fn("one", "two"); //['one', 'two']
```

---

### for...in Vs for...of loop

Difference is about what are you looking for: "key properties, arrays, set, map or values" or "index(s)".

### for...of

iterates over: Array, arguments, Set, Map and "custom iterable objects like generators". IF WE NEED TO iterate Objects, so for..of CANNOT be used on Objects,
but we can use GENERATORS.

```js
var arr = [3, 5, 7, 9],
  obj = { a: 1, b: 2, c: 3 };
objArr = [{ a: 1 }, { b: 2 }, { c: 3 }];

for (let n of arr) {
  console.log(n);
} // 3,5,7,9

for (let n of obj) {
  console.log(n);
} // ERROR
```

```js
// we need to use generators: there is any way to do iterate through JSON using JS, we need generators
function entries(obj) {
  for (let key of Object.keys(obj)) {
    yield[(key, obj[key])];
  }
}
for (let [key, value] of entries(obj)) {
  console.log(key, "->", value);
}

for (let n of objArr) {
  console.log(n);
} // {a:1},{b:2},{c:3}
```

### for...in loop

This is different from the for...in operator, it is like a little brother, an old version:

- iterates over an Array but "you get indexes, NOT values".
- iterates over Objects, but returns the property names/keys, not values.

```js
var arr = [3, 5, 7, 9],
  obj = { a: 1, b: 2, c: 3 };
objArr = [{ a: 1 }, { b: 2 }, { c: 3 }];
for (var p in arr) {
  console.log(p);
} // 0,1,2,3 (return index(s))

for (var p in obj) {
  console.log(p);
} // a,b,c (return properties/keys not values)

for (var p in objArr) {
  console.log(p);
} // 0,1,2 (return index(s))
```

```js
// looping and iterating Object
obj = { a: 1, b: 2, c: 3 };
// ES5 for..in over objects
for (let p in obj) {
  console.log(p); // p = a, b, c
} // a,b,c
```

```js
// looping and iterating Array
var arr = [3, 5, 7, 9];
for (let p in arr) {
  // p = [0,1,2,3]
  console.log(p, arr);
}
//[3, 5, 7, 9]
//[3, 5, 7, 9]
//[3, 5, 7, 9]
```

---

### toEqual vs toBe

```js
.toEqual() == .toBe() ===
```

```js
toEOperator == is a has a function and === is has a different function goal.
work for objects toBe() compares with ===
```

---

## Adding objects to out main Object.

```js
const LEO = "Leo";
(function (LEO) {
  LEO = function (options) {
    var defaults = {
        account: {
          paymentPin: { set: false, enabled: false },
          parentalPin: { set: false, enabled: false },
        },
      },
      settings = LEO.extend(defaults, options);

    return (this.prototype = {
      account: settings.account,
    });
  };
})(LEO);
```

---

### new() vs Object Literals:

```js
// ❌ instead of 💩
var lunch = new Array();
lunch[0] = "Dosa";
lunch[1] = "Roti";
lunch[2] = "Rice";
lunch[3] = "what the heck is this?";

// better do ✅
var lunch = ["Dosa", "Roti", "Rice", "what the heck is this?"];
```

---

### variable definition shortcut

```js
// old style
var n1 = 1;
var n2 = function () {};
var n3 = n2(n1);

// better do ✅
var n1 = 1,
  n2 = function () {},
  n3 = n2(n1);
```

---

### "Keyword Arguments" technique

Imagine you have multiple arguments and most are optional arguments. The function call becomes really terrifying!
In JS it is implemented with a parameters object:

```js
function showWarning(options) {
  var width = options.width || 200; // defaults
  var height = options.height || 100;
  var title = options.title || "Warning";

  alert(width + height + title);
}
```

```js
showWarning({
  contents: "Text",
  showYesNo: true,
}); // 300Warning
```

> Another bonus is that the arguments object can be reconfigured and reused:

```js
const opts = {
  width: 400,
  height: 200,
  contents: "Text",
  showYesNo: false,
};
showWarning(opts); // 600Warning

>  And then reuse it again:

opts.contents = "Another text";
showWarning(opts); // 600Warning
```

---

### .fetch() native 

#### Use Fetch to Make AJAX Calls in JavaScript

```js
const url = "https://api.github.com/users/leolanese/repos";

fetch(url)
  .then((response) => response.json())
  .then((repos) => {
    const reposList = repos.map((repo) => repo.name);
    console.log(reposList);
  })
  .catch((err) => console.log(err));
```

#### To send a POST request, here's how the method parameter can be used with async / await syntax.

```js
const params = {
  id: 123,
};

const response = await fetch("url", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(params),
});

const data = await response.json();
```

---

### set few variables to undefined: remove a property of an Object

```js
// ❌ instead of 💩
this.setup.selection.gem_colour = undefined;
this.setup.selection.gem_cut = undefined;
this.setup.selection.gem_clarity = undefined;

// better do ✅
// delete doen't delete, just undefine it
delete this.setup.selection.gem_colour;
delete this.setup.selection.gem_cut;
delete his.setup.selection.gem_clarity;
```

---

### window.location url path

```js
https://www.leolanese.com:8080/auth/?filter=JS#666

// Properties
window.location.origin   → 'https://www.leolanese.com'
        .protocol → 'https:'
        .host     → 'www.leolanese.com:8080'
        .hostname → 'www.leolanese.com'
        .port     → '8080'
        .pathname → '/auth/'
        .search   → '?filter=JS'
        .hash     → '#666'
        .href     → 'https://www.leolanese.com/auth/?filter=JS#666'


window.location
	.origin	Base URL (Protocol + hostname + port number)
	.protocol	Protocol Schema (http: or https)
	.host	Domain name + port
	.hostname	Domain name
	.port	Port Number
	.pathname	The initial '/' followed by the Path
	.search	? followed by Query String
	.hash	# followed by the Anchor or Fragment identifier
	.href	Full URL


// methods
window.location.assign('url')
        .replace('url')
        .reload()
        .toString()
```

---

### Delete Operator

Rule is when defined non-configurable, it cannot be deleted

#### var, let, const and delete

var, let and const declare non-configurable properties. So that's why variables declared with var, let or const cannot be removed from the global scope.

```js
const obj = {
  a: function () {
    console.log("test");
  },
};

obj.a();
Object.defineProperty(obj, "a", { configurable: false });
delete obj.a;
obj.a(); // test test
```

---

#### delete and the prototype chain

> Rule: delete in an object does not descend the prototype chain.

```js
function Foo() {
  this.bar = 90;
}
Foo.prototype.bar = 88;
const f = new Foo();
f.bar; // 90
delete f.bar; // deletes the bar in Foo, but not in its prototype.
f.bar; // 88
```

```js
const Mal = {
  alimo: "test",
};
var ya = Object.create(Mal);
delete ya.alimo; // deletes the alimo in Ya, but not in its prototype.
ya.alimo; // "test"
```

---

### Do not use delete to remove an item from array

```js
// ❌ instead of 💩
var items = [12, 548, "a", 2, 5478, "foo", 8852, , "Doe", 2154, 119];

items.length; // return 11
delete items[3]; // 2 will be undefined
items.length; // return 11
/* [12, 548, "a", undefined × 1, 5478, "foo", 8852, undefined × 1, "Doe", 2154, 119]   */

// better do ✅
var items = [12, 548, "a", 2, 5478, "foo", 8852, , "Doe", 2154, 119];

items.length; // return 11
items.splice(3, 1); // 2 will be removed
items.length; // return 10
/* [12, 548, "a", 5478, "foo", 8852, undefined × 1, "Doe", 2154, 119]   */
```

---

### remove defined positions from array

```js
const valuesArr = ["v1", "v2", "v3", "v4", "v5"];
const toBeRemoveFromIndex = [0, 2, 4];
const indexSet = new Set(toBeRemoveFromIndex);
const arrayWithValuesRemoved = valuesArr.filter((value, i) => !indexSet.has(i));

console.log(arrayWithValuesRemoved); // ["v2", "v4"]
```

---

### remove defined position objects from array of objects

```js
const valuesArr = [{ 1: 1 }, { 2: 2 }, { 3: 3 }, { 4: 4 }, { 5: 5 }];
const toBeRemoveFromIndex = [0, 2, 4];
const indexSet = new Set(toBeRemoveFromIndex);
const arrayWithValuesRemoved = valuesArr.filter((value, i) => !indexSet.has(i));

console.log(arrayWithValuesRemoved); // [{2: 2}, {4: 4}]
```

---

### Resting arguments

```js
const fn = (...args) => console.log(args);

fn(1, 2, 3); //[1, 2, 3]
fn("one", "two"); //['one', 'two']
```

---

### Factory Functions

> A factory function is any function which is not a class or constructor that returns a (presumably new) object.

> In JavaScript, any function can return an object. When it does so without the new keyword, it's a factory function.

> object destructuring with Object literals support concise method syntax

```js
const createUser = ({ userName, avatar }) => ({
  userName,
  avatar,
  setUserName(userName) {
    this.userName = userName;
    return this;
  },
});
console.log(createUser({ userName: "echo", avatar: "echo.png" }));

/**
{
  "avatar": "echo.png",
  "userName": "echo",
  "setUserName": [Function setUserName]}
*/
```

---

### shorthands: fat arrow function/lambda


```js
// IIFE
(function () {
  // code goes here...
})();

(() => {
  // code goes here...
})();
```

```js
f = (function () {
  return function () {
    return "IIFE";
  };
})();
alert(f());

var Init;
(Init = function Init() {
  alert("wee");
})();
```

```js
// ANONIMOUS function (no IIFE)
(function () {});
() => {};
```

```js
// FS:
// 1
function foo() {}
var myFn = function (x) {
  return x + 1;
};
let myFn = (x) => {
  return x + 1;
};

//2
function sayMyName(name) {
  alert(`Hello ${name}`);
}
const sayMyName = (name) => {
  alert(`Hello ${name}!`);
};
sayMyName("Leo");
```

```js
// FE
//1
var foo = function () {};
let foo = () => {};

// 2
var a = function a() {};
var a = () => {};

//3
var a = function a(b) {
  return b;
};
var a = (b) => b;

//4
var sum = function sum(a, b) {
  return a + b;
};
let sum = (a, b) => a + b;
```

---

## IIFE

```js
Self-invoking Functions
(
  function(){
   alert('boo');
  }
)(); // execute now
```

```js
(
  function(name){
   alert('Hello ' + name + '!');
  }
)('Leo'); // execute now using this value as parameter
```

---

## `FD`, `FE` and `arrow function`

### FD:  must begin/declared with `function` (must declare is a function)

```js
function add(a, b) {
    return a + b;
}
```

### FE: Assigns a function to a variable or a property

```js
const add = function(a, b) {
    return a + b;
};
```

### Arrow Function: anonimous

```js
const add = (a, b) => a + b;
```

---

### Function Declaration are 'hoisting'. FD: and FE:

> FD: ARE hoisting the function definition means are declared on top of the scope.
> FE: NOT hoisted, or already declared as undefined and need to be invoque to contain something

```js
// FE: 'Function Expressions' are NOT hoisted:
notHoisted(); // Uncaught TypeError: notHoisted is not a function
var notHoisted = function () {
  console.log("bar");
};

// FS: 'function statement' can use it before you declared it because ARE hoisted
hoisted(); // logs "foo"
function hoisted() {
  console.log("foo"); // foo
}
```

---

## Better for loops / no for loops

The for loop's design encourages mutation of state and usage of side effects, both of which are potential sources of buggy and unpredictable code.

```js
// old school for loops
const cats = [
  { name: "Mojo", months: 84 },
  { name: "Mao-Mao", months: 34 },
  { name: "Waffles", months: 4 },
  { name: "Pickles", months: 6 },
];
var kittens = [];
// typical poorly written `for loop`
for (var i = 0; i < cats.length; i++) {
  if (cats[i].months < 7) {
    kittens.push(cats[i].name);
  }
}
console.log(kittens); // ["Waffles", "Pickles"]

// better do ✅
const isKitten = (cat) => cat.months < 7;
const getName = (cat) => cat.name;
const getKittenNames = (cats) => cats.filter(isKitten).map(getName);
const cats = [
  { name: "Mojo", months: 84 },
  { name: "Mao-Mao", months: 34 },
  { name: "Waffles", months: 4 },
  { name: "Pickles", months: 6 },
];
const kittens = getKittenNames(cats);
console.log(kittens); // ["Waffles", "Pickles"]
```

---

## event delegation (not just on list)

the .toggle-display class is a `<li>` containing different tags, we determinate where we are going to assign the class: `event.target.nodeName === 'A'`

```js
$(".toggle-display").on("click", function () {
  // event delegation here otherwise we're binding every element
  if (event.target.nodeName === "A" || event.target.nodeName === "a") {
    var toggle = document.querySelector(".btn-toggle-display");
    toggle.classList
      ? this.classList.toggle("toggle-display-no")
      : $(this).toggleClass("toggle-display-no");
  }
});
```

## event delegation referencing the elements that detect the "event":

- event.currentTarget:
  is the same as 'this' - it refers to the element that the listener function is attached to (if the same function is attached as a listener to several elements, it will be a reference to the listener that is currently being run).

- event.target:
  is the element that the event actually happened to. In the case of the earlier example, this would be the link. If there was a span inside the link, and you clicked that, then eventObject.target would be a reference to the span, even if the span itself did not have any listeners attached directly to it.

- event handling "delegation":
  addEventListener can take an object as a second argument that will look for a method called handleEvent and call it:

```js
var obj = {
  init: function () {
    document.getElementById("btn").addEventListener("click", this, false);
    document.getElementById("btn").addEventListener("touchstart", this, false);
  },
  handleEvent: function (e) {
    switch (e.type) {
      case "click":
        this.button();
        break;
      case "touchstart":
        this.button();
        break;
    }
  },
  dude: "holla",
  button: function () {
    alert(this.dude);
  },
};

obj.init();
```

Another awesome thing we can do is change the buttons behaviour without having to remove and re-attach the event handler:

```js
handleEvent: function(e) {
      var evt = e || window.event,
          t = evt.target || evt.srcElement;

      switch(evt.type) {
          case "click":
              if (t.id === "btn") {
                  this.button();
              } else if(t.id === "btn2") {
                  this.changeHandleEvent(evt);
              } else {
                  this.revertHandleEvent();
              }
              break;
          case "touchstart":
              this.button();
              break;
          case "contextmenu":
              this.other(evt);
              break;
      }
}
```

* LINK:
- http://www.thecssninja.com/demo/handleEvent/


---

## Using the Method Initializer Shorthand

A new shorthand notation is available for adding a method to an object where the keyword function is no longer necessary.

```js
// Old way
isActive: function(){
 return postCount >= ACTIVE_POST_COUNT
}
```

```js
function foo(first, last, n) {
  let fullName = first + " " + last;
  const ACTIVE_POST_COUNT = 10;
  return {
    first,
    last,
    fullName,
    isActive() {
      return n >= ACTIVE_POST_COUNT;
    },
  };
}

console.log(foo().isActive()); // false
```

---

## MIXIN classes ES6

> the following two functions Storage and Validation are mixins:

```js
const Storage = Sup => class extends Sup {
   save(database) { ··· }
};
const Validation = Sup => class extends Sup {
   validate(schema) { ··· }
};
```

That allows you to implement a mixin as a function that maps a class C to a new class (with the mixin methods) whose superclass is C.

---

## clean memory using garbache collector

We need to destroy every object we are not using any more.
In order to our memory usage, we set to null, so the garbage collector will destroy will destroy it:

```js
// do some thing with the object
var oObje = new Object();

// set to null = there are no longer any references to the object.
oObj = null;
```

---

## for-in loop

```js
const fruits = ['apple', 'peach', 'banana'];

for(let fruit in fruits) {
    console.log(fruits[fruit])
}; // 'apple', 'peach', 'banana'
```

```js
const prop,
  obj = { name: "Joe", job: "Coder", age: 25 };

for (var prop in obj) {
  console.log(prop + ": " + obj[prop]);
}; // name: "Joe", job: "Coder", age: 25
```

## for-in loop + "hasOwnProperties":

```js
const prop,
  obj = { name: "Joe", job: "Coder", age: 25 };

for (var prop in obj) {
  if (obj.hasOwnProperty(prop)) {
    console.log(prop + ": " + obj[prop]);
  }
}
```

## for-in loop + "typeof"

```js
const obj = { name: "Joe", job: "Coder", age: 25 };

for (var prop in obj) {
  if (typeof obj[prop] !== "function") {
    console.log(prop + ": " + obj[prop]);
  }
}; // name: "Joe", job: "Coder", age: 25
```

```js
(function () {
  var newBabeBorn,
    obj = {
      Name: "Tom Lanese",
      Cry: "All the time",
      Sleeping: "1.5hs",
      Feeding: "45m",
      Feeling: "Very Happy",
    };

  function myLifeTheseDays() {
    for (var newBabeBorn in obj) {
      if (obj.hasOwnProperty(newBabeBorn)) {
        console.log(newBabeBorn + ": " + obj[newBabeBorn]);
      }
    }
  }

  myLifeTheseDays();
})();
// Tom Lanese 
// Cry: All the time
// Sleeping: 1.5hs
// Feeding: 45m
```

---

## Create & initiate Object

```js
function createPerson({
  name = "Leo",
  familyName = "Lanese",
  height = 175,
  weight = 85,
  age = 40,
} = {}) {
  return {
    name,
    familyName,
    height,
    weight,
    age,
  };
}

const aPerson = createPerson();
// {name: 'Leo', familyName: 'Lanese', height: 175, weight: 85, age: 40}
```

---

## replace loops in FP in arrays

```js
// instead of
var names = ["Sonny", "Joel", "Isabelle", "Henry"];

for (var i = 0; i < names.length; i++) {
  console.log("Hello " + names[i]);
}
```

```js
// better do
const names = ["Sonny", "Joel", "Isabelle", "Henry"];

names.map((element, index, array) => { 
  console.log('element: ' + element + ", index: " + index + ", array: " + array);
})
// element: Sonny, index: 0, array: Sonny,Joel,Isabelle,Henry
// element: Joel, index: 1, array: Sonny,Joel,Isabelle,Henry
// element: Isabelle, index: 2, array: Sonny,Joel,Isabelle,Henry
// element: Henry, index: 3, array: Sonny,Joel,Isabelle,Henry
```

---

## use JSON native Object instead string concatenation

```js
const test = '{"name":"Leo","subname":"lanese"}';
const n = JSON.parse(test);
n.name; //"Leo"

JSON.stringify(n, 4, 4); 
// '{\n    "name": "Leo",\n    "subname": "lanese"\n}'
```

---

## cross compare between array of objects. Intersection.

```js
const REF = [
  {
    country: "UK",
    description: "United Kingdom",
  },{
    country: "USA",
    description: "United States Of America",
  },
];

const formattedCountries = new Map(REF.map(({ country, description }) => [country, description]));

const DATA = [
  {
    name: "AAA",
    place: "London",
    country: "UK",
  },
  {
    name: "BBB",
    place: "NewYork",
    country: "USA",
  },
];

const reformattedArray = DATA.map(({ country, ...rest }) => ({
  ...rest,
  country: formattedCountries.get(country),
}));

// {name: 'AAA', place: 'London', country: 'United Kingdom'}
// {name: 'BBB', place: 'NewYork', country: 'United States Of America'}
```

---

## Copy object

```js
// ❌ instead of 💩
let user = { name: "bytefish", url: "https://www.leolanese.com" };
copy = Object.assign({}, user);

// better do ✅
let user = { name: "bytefish", url: "https://www.leolanese.com" };
copy = { ...user };
```

---

## Adds elements to the beginning or end of an array

```js
// ❌ instead of 💩
let arr = [3];
arr.unshift(1, 2);
arr.push(4, 5);
console.log(arr); // [1, 2, 3, 4, 5]

// better do ✅
let arr = [3];
copy = [1, 2, ...arr, 4, 5]; // [1, 2, 3, 4, 5]
```

---

## union array of objects. Union

```js
let p1 = [{ name: "Leo Lanese" }];
let p2 = [{ tag: "JS" }];

p3 = [{ ...p1, ...p2 }]; // [{name: "Leo Lanese"}, {tag: "JS"}]
```

---

## elements of `arr1` that are not in `arr2`. Difference

```js
// eg1
let arr1 = [1, 2, 3, 4, 5];
let arr2 = [5, 6, 7, 8];
let b = new Set(arr2);
let difference = [...arr1].filter((x) => !b.has(x));

console.log(difference); // [ 1, 2, 3, 4 ]
```

```js
// eg2
let arr1 = [1, 2, 3, 4, 5];
let arr2 = [5, 6, 7, 8];
let difference = arr1.filter((x) => !arr2.includes(x));

console.log(difference); // [ 1, 2, 3, 4 ]
```

---

## ratio. Count the number of positive, negative, and zero values in the array using the reduce function

```js
const a = 3;
const b = 5;

// Ratio as a fraction
const ratioFraction = `${a}/${b}`; // "3/5"

// Ratio as a decimal
const ratioDecimal = a / b;  // 0.6
```

```js
const arr = [-4, 3, -9, 0, 4, 1]

function plusMinus(arr){
   let pos = 0
   let neg = 0
   let zero = 0
   const len = arr.length 
    
   const counters = arr.reduce((acc, value, index)=>{
       // console.log(acc, value, index)
       if (value > 0) {
           pos = pos + 1
           // console.log('this.pos', this.pos)
        } else if (value < 0) {
            neg = neg + 1;
        } else {
            zero = zero + 1;
        }
       return  acc
   }, 0)

    console.log(pos / len + "\n" + neg / len + "\n" + zero / len);           
}
```

---

## staircase

```js
/*
 * Complete the 'staircase' function below.
 *
 * The function accepts INTEGER n as parameter.
 * 
 * input: 2
 * output:   #
 *          ##
 */

function staircase(n) {
    // Write your code here
    const lines = n
}
```

---

## Get elements which belongs either to A or to B array but not to both. Symmetrical Difference. Utility

```js
// eg1
const A = [1, 2, 3, 4, 5, 6, 7, 8];
const B = [1, 3, 5, 6, 7, 8, 9];

const symmetricalDifference = (arr1, arr2) => {
  const res = [];
  for (let i = 0; i < arr1.length; i++) {
    if (arr2.indexOf(arr1[i]) !== -1) {
      continue;
    }
    res.push(arr1[i]);
  }
  for (let i = 0; i < arr2.length; i++) {
    if (arr1.indexOf(arr2[i]) !== -1) {
      continue;
    }
    res.push(arr2[i]);
  }
  return res;
};

console.log(symmetricalDifference(A, B)); // [2, 4, 9]
```

```js
// eg2
const A = [1, 2, 3, 4, 5, 6, 7, 8];
const B = [1, 3, 5, 6, 7, 8, 9];

A.filter((x) => !B.includes(x)).concat(B.filter((x) => !A.includes(x))); // [2, 4, 9]
```

---

## sum all arguments

```js
// option 1
function sum(...arr) {
  return arr.reduce((acc, cur) => acc + cur);
}

sum(1, 2, 3, 4); // 10
sum(1, 3, 5, 7); // 16;
```

```js
// option 2
 function aVeryBigSum(ar) {
   return ar.reduce((previous, current, index) => {
     const val = previous + current;
   
     return val;
   }, 0);
}

aVeryBigSum([2,1,2]); // 5
```

---

## Searching in array

```js
const fruits = ["apple", "banana", "grapes", "mango", "orange"];

/**
 * Filter array items based on search criteria (query)
 */
function filterItems(arr, query) {
  return arr.filter((el) => el.toLowerCase().includes(query.toLowerCase()));
}

console.log(filterItems(fruits, "ap")); // ['apple', 'grapes']
console.log(filterItems(fruits, "an")); // ['banana', 'mango', 'orange']
```

---

## Filtering invalid entries from JSON


```js
const arr = [
  { id: 15 },
  { id: -1 },
  { id: 0 },
  { id: 3 },
  { id: 12.2 },
  {},
  { id: null },
  { id: NaN },
  { id: "undefined" },
];

let invalidEntries = 0;

function filterByID(item) {
  if (Number.isFinite(item.id) && item.id !== 0) {
    return true;
  }
  invalidEntries++;
  return false;
}

const arrByID = arr.filter(filterByID);

console.log("Filtered Array\n", arrByID);
// Filtered Array
// [{ id: 15 }, { id: -1 }, { id: 3 }, { id: 12.2 }]
```

---

## Matrix. Calculate sumatory first diagonal - sumatory secondary diagonal

```js
function diagonalDifference(arr) {
    // also needs to return absolute number
    const res = Math.abs(primaryDiagonalSum(arr) - secondaryDiagonalSum(arr));
    return res;
}

function primaryDiagonalSum(arr) {
    return arr.reduce((sum, row, index) => {
        return sum + row[index];
    }, 0);
}

function secondaryDiagonalSum(arr) {
    return arr.reduce((sum, row, index) => { 
        return sum + row[arr.length - 1 - index]
    }, 0);
}
```



---

## 2D array (two-dimensional array) - 2D_INTEGER_ARRAY - 3 x 3

// each set of square brackets [...] represents a row in the 2D array, and the entire set of square brackets [[...], [...], [...]] represents the 2D array itself.

```js
function diagonalDifference(arr) {
    debugger;
    console.log(arr);
}

diagonalDifference([[1, 2, 3], [4, 5, 6], [7, 8, 9]]);
```

---

## get min and max from Array

```js
let arr = [23, 34, 53, 3];

console.log(Math.max(...arr)); // 53
console.log(Math.min(...arr)); // 3
```

---

## Spread Operator Shorthand: joining as cloning arrays

```js
// ❌ instead of 💩
// joining arrays
const odd = [1, 3, 5];
const nums = [2, 4, 6].concat(odd);

// cloning arrays
const arr = [1, 2, 3, 4];
const arr2 = arr.slice();

// better do ✅
// joining arrays
const odd = [1, 3, 5];
const nums = [2, 4, 6, ...odd];
console.log(nums); // [ 2, 4, 6, 1, 3, 5 ]

// cloning arrays
const arr = [1, 2, 3, 4];
const arr2 = [...arr];
```

## Initialize / Unpack, rename and assign defaults

```js
const obj = {
  foo: 1,
  bar: 0,
  baz: undefined,
};

// unpack, rename, and assign defaults
const {
  foo: apple = 500,
  bar: banana = 501,
  baz: orange = 502,
  qux: mango = 503,
} = obj;

apple; // 1
banana; // 0
orange; // 502
mango; // 503
```

---

### Unpacking objects passed as a function parameter

```js
const book = {
  title: 'Some Great Book',
  author: {
    firstName: 'Seymour',
    lastName: 'Penman',
  },
};
function getAuthorName({author: { firstName, lastName}) {
  return `The author is ${firstName} ${lastName}`;
};

logAuthorName(book); // 'The author is Seymour Penman'
```

---

### Rest and Spread look the same

Rest parameters and the spread operator look the same, but the former is used
in function definitions and the latter in function invocations.

```js
// Function definition: rest
function displaytags(...tags){
 for(let i in tags){
   ..
 }
}
```

```js
// Function invocation: spread
getRequest("/topics/17/tags", function () {
  let tags = data.tags;
  displayTags(...tags);
});
```

---

## Destructuring assignment

> Extracts properties from an object.

```js
const person = {
  myName: "Leo",
  age: 47,
  size: {
    height: 1.7,
    weight: 85,
  },
};

const { myName, age } = person;
	
console.log(`${myName} is ${age} years old.`);  // Leo is 47 years old
```

---

## Destructuring assignment

> Extract object property and array from a complex object. 

```js
const ao = {
  op1: "JS",
  op2: [
    { name: "Leo" },
  ],
};

const { op1, op2 } = ao;

// { op1 = 'JS', op2 = [{ name: 'Leo' }]
```

---

## Destructuring assignment

> Initialization / Extract object property and array item from a complex object. 

```js
const avengers = {
  mission: "Assemble",
  members: [
    { name: "Tony Stark", alias: "Iron Man" },
    { name: "Steve Rogers", alias: "Captain America" },
    { name: "Natasha Romanoff", alias: "Black Widow" },
  ],
};

const {
  mission: teamMission,
  members: [, { name: capName, alias: capAlias }, { name: blaName, alias: blaAlias }],
} = avengers;

teamMission; // 'Assemble'
capName; // 'Steve Rogers'
capAlias; // 'Captain America'
blaName; // 'Natasha Romanoff'
blaAlias; // 'Black Widow'
```

---

## Destructuring and Rest

> Easily extract `array elements` & `object properties` and store them in variables

> Destructuring cover: `Array Destructuring` and `Object Destructuring`

### Destructuring difference with Spread operator

The spread operator has exactly the same syntax as the rest operator – three dots.
But they are different: the former contributes data to Array literals and function calls, whereas the latter is used for destructuring and extracts data.

---

## `Array` destructuring

#### Variable assignment

```js
// Variable assignment
const foo = ["one", "two", "three"];

const [one, two, three] = foo;
console.log(one); // "one"
console.log(two); // "two"
console.log(three); // "three"

const arr1 = [0, 1];
const arr2 = [2, 3];

const copyOfArr1 = [...arr1];
const concatenating = [...arr1, ...arr2]; // [0, 1, 2, 3]
```

#### Swapping variables

```js
let a = 1;
let b = 3;

[a, b] = [b, a];
console.log(a); // 3
console.log(b); // 1
```

#### Create elements from [Array]

```js
const names = [
  "Jack",
  "Janet",
  "John",
  "Jessie",
  "Jaqueline",
  "Jerry",
  "Justin",
  "Julie",
  "Jake",
];

const [first, second, third, ...theRest] = names;

first; // "Jack"
theRest; // ["Jessie", "Jaqueline", "Jerry", "Justin", "Julie", "Jake"]
```

---

## Assigning From Array to Local Variables

We typically access array elements by their index, but doing so for more than just a couple of elements can quickly
turn into a repetitive task.

```js
let users = ["Leo", "and", "Carley"];

let a = users[0];
let b = users[1];
let c = users[2];

// better
// Reading Values With Array Destructuring
// We can use destructuring to assign multiple values from an array to local variables.

let users = ["Leo", "and", "Carley"];
let [a, b, c] = users;
console.log(a, b, c);

// or even better
// Combining Destructuring With Rest Params
let users = ["Leo", "and", "Carley"];
let [first, ...rest] = users; // groups remaining arguments in an array
console.log(first, rest); // Leo ["and", "Carley"]
```

---

#### Accessing elements inside Array

```js
const arr = ["a", "b", "c", "d"];
const { 0: first, 1: second, 2: third, 3: forth, tenth = "z" } = arr;

first; // a
second; // b
third; // c
forth; // d
tenth; // z
```

---

## Destructuring in a for-of loop

```js
const arr = ["a", "b"];
for (const [index, element] of arr.entries()) {
  console.log(index, element);
}
// 0 a
// 1 b
```

---

## Copy variables from array

```js
//  allows you to
const [first, second] = [1, 2, 3, 4];
// first: 1
// second: 2

const [head, ...tail] = [1, 2, 3];
// head: 1
// tail: [ 2, 3 ]
```

---

## Delete elements from the beginning of an Array

```js
const numbers = [1, 2, 3];
const [, ...fooNumbers] = numbers;

fooNumbers; // [2, 3]
numbers; // [1, 2, 3] numbers array is not mutated
```

---

## Object destructuring. Variable assignment

```js
const o = { p: 42, q: true };
const { p, q } = o;

console.log(p); // 42
console.log(q); // true

const ob1 = { name: "mark" };
const ob2 = { surname: "smith" };

const copyOfOb1 = { ...ob1 };
const concatenating = { ...ob1, ...ob2 }; // { name: 'mark', surname: 'smith' }
```

#### Object initialization with function

```js
function buildUser(first, last) {
  let fullName = first + " " + last;
  return { first: first, last: last, fullName: fullName };
}

let { first, last, fullName } = buildUser("Leo", "Lanese");
first; // Leo
last; // Lanese
fullName; // Leo Lanese
```

---

## Delete property from the Object

```js
const big = {
  foo: "value Foo",
  bar: "value Bar",
};
const { foo, ...small } = big; // { bar: 'value Bar' }
const { bar, ...small2 } = big; // {foo: "value Foo"}

big; // { foo: 'value Foo', bar: 'value Bar' } big object is not mutated
```

---

## Object destructuring when declaring new variable

```js
const geolocation = { long: 1.42, lat: 42.1 };
// Slow to type
const long = geolocation.long;
const lat = geolocation.lat;
// Fast
const { long, lat } = geolocation;
```

---

## Initialize / Create elements from an Object

```js
const apple = {
  numberOfLeaves: 2,
  colors: {
    actual: ["green", "yellow"],
    possible: ["red", "green", "yellow"],
  },
  kind: "Golden Delicious",
  sku: "A-GD-01",
};

// ❌ instead of 💩
// const kind = apple.kind;
// const sku = apple.sku;

const { kind, sku } = apple;
kind; // "Golden Delicious"
sku; // "A-GD-01"

// ❌ instead of 💩
// const colors = apple.colors.actual;
// const possibleColors = apple.colors.possible;
const { actual: colors, possible: possibleColors } = apple.colors;
colors; // ["green", "yellow"]
possibleColors; // ["red", "green", "yellow"]
```

---

## Walk through object

> Creates a generator, that walks through all the keys of a given object.

```js
const walkThrough = function* (obj) {
  const walk = function* (x, previous = []) {
    for (let key of Object.keys(x)) {
      if (typeof x[key] === 'object') yield* walk(x[key], [...previous, key]);
      else yield [[...previous, key], x[key]];
    }
  };
  yield* walk(obj);
};

const obj = {
  a: 10,
  b: 20,
  c: {
    d: 10,
    e: 20,
    f: [30, 40]
  },
  g: [{
      h: 10,
      i: 20},
    {
      j: 30
    },
    40
  ]
};
[...walkThrough(obj)]; // [Array(2), Array(2), Array(2), Array(2), Array(2), Array(2), Array(2), Array(2), Array(2), Array(2)]
```

---

## Find first matching key

> Finds the first key that satisfies the provided testing function. Otherwise undefined is returned

```js
const findKey = (obj, fn) =>
  Object.keys(obj).find(key => fn(obj[key], key, obj));

findKey(
  {
    barney: { age: 36, active: true },
    fred: { age: 40, active: false },
    pebbles: { age: 1, active: true }
  },
  x => x['active']
); // 'barney'
```

---

### Omit object properties based on function

> Omits the key-value pairs corresponding to the keys of the object for which the given function returns falsy.

const omitBy = (obj, fn) =>
  Object.keys(obj)
    .filter(k => !fn(obj[k], k))
    .reduce((acc, key) => ((acc[key] = obj[key]), acc), {});

omitBy({ a: 1, b: '2', c: 3 }, x => typeof x === 'number'); // { b: '2' }

---

#### Destructuring in function parameters

```js
function createAvenger(avengerName, realName, height, weight, age) {
  return {
    avengerName: avengerName,
    realName: realName,
    height: height,
    weight: weight,
    age: age,
  };
}
var ironMan = createAvenger("Iron Man", "Tony Stark", 1.85, 102, 46); // {avengerName: "Iron Man", realName: "Tony Stark", height: 1.85, weight: 102, age: 46}
```

```js
function createAvenger({ avengerName, realName, height, weight, age }) {
  return {
    avengerName,
    realName,
    height,
    weight,
    age,
  };
}
const ironManOpts = {
  avengerName: "Iron Man",
  realName: "Tony Stark",
  height: 1.85,
  weight: 102,
  age: 46,
};
const ironMan = createAvenger(ironManOpts); //  { "age": 46, "avengerName": "Iron Man","height": 1.85, "realName": "Tony Stark", "weight": 102 }
```

---

## Access Nested Properties and Set Default Values

```js
const person = {
  name: "Leo",
  work: {
    job: "Developer",
  },
};
const { name: name } = person;
name; // Leo

const {
  work,
  work: { job },
} = person;
work; // {job: "Developer"}
```

---

## Using Computed Properties in Destructuring

```js
const person = {
  name: "Leo",
  work: {
    job: "Developer",
  },
};

let name = "name";
const { [name]: username } = person;
username; // Leo

let work = "work";
const { [work]: job } = person;
job; // {job: "Developer"}
```

---

## destructuring on the parameters of a function definition

```js
//  We can use destructuring on the parameters of a function definition:
function something([first, ...rest]) {
  i;
  return {
    first: first,
    rest: rest,
  };
}
var result = something([1, 2, 3]); // result: { first: 1, rest: [ 2,3 ] }
```

---

## Destructuring returned Arrays

```js
const [all, year, month, day] = /^(\d\d\d\d)-(\d\d)-(\d\d)$/.exec("2999-12-31"); //

const [, year, month, day] =
  /^(\d\d\d\d)-(\d\d)-(\d\d)$/.exec("2999-12-31") || [];
```

---

## Destructuring array:

```js
const [ num0, ...others ] = [ 1, 2, 3, 4, 5, 6 ]

console.log(num0) // 1
console.log(others) // [2, 3, 4, 5, 6]
```

---

## Destructuring object

```js

const obj = { name: 'fatfish', age: 100, luckyNumber: 6 }
const { name, ...other } = obj

console.log(name) // fatfish
console.log(other) // { age: 100, luckyNumber: 6 }
```


---

## Object destructuring when declaring new variable

> Using it on arrays

```js
const geolocation = [1.42, 42.1];

// Slow to type
const long = geolocation[0];
const lat = geolocation[1];

// Fast
const [long, lat] = geolocation;
```

---

## extract data from one variable to another by using structure

```js
var [first, second] = [1, 2, 3, 4];
// first: 1
// second: 2

var [head, ...tail] = [1, 2, 3];
// head: 1
// tail: [ 2, 3 ]
```

---

## Destructuring dynamic properties

```js
function greet(obj, nameProp) {
  const { [nameProp]: name = "Unknown" } = obj;
  return `Hello, ${name}!`;
}

greet({ name: "Batman" }, "name"); // 'Hello, Batman!'
greet({}, "name"); // 'Hello, Unknown!'
```

---

## Swapping Variables Using Destructuring Expressions

// 2 values

```js
// ❌ instead of 💩
let a = 1;
let b = 2;
let temp;

temp = a;
a = b;
b = temp;
```

```js
// using destruturing
[a, b] = [b, a];
```

// 3 values

```js
let zero = 2;
let one = 1;
let two = 0;

[zero, one, two] = [two, one, zero];

zero; // 0
one; // 1
two; // 2
```

---

## Destructuring Regular Expressions. exec

```js
const email = "user.name@address.com";
const [originalString, username, address, tld] =
  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/.exec(email);
```

```js
let datePattern = /^([a-z]+)\s+(\d+)\s*,\s+(\d{4})$/i;
let matchResult = datePattern.exec("June 24, 2015");

let [all, month, day, year] = datePattern.exec("June 24, 2020") || [];

day; // 24
month; // June
year; // 2020
all; // "June 24, 2020"
```

---

## Destructuring assignment syntax with Objects

```js
const car = {
  brand: "ferrari",
  type: "sportscar",
  horsepower: 600,
  wheels: 4,
};

const { brand, type } = car;

console.log(brand); // ferrari
console.log(type); // sportscar
```

---

## Destructoring helping Immutable asignation

```js
const big = {
  foo: "value Foo",
  bar: "value Bar",
};

const { foo, ...small } = big;

small; // { bar: 'value Bar' }
big; // { foo: 'value Foo', bar: 'value Bar' }
```

---

## destructoring best practices

```js
const { x: x, y: y } = { x: 11, y: 8 }; // x = 11, y = 8
```

```js
const { x, y = 1 } = {}; // x = undefined; y = 1
```

```js
// ❌ instead of 💩
const { prop: x } = { prop: 123 }; // 123

// better do ✅
const { prop: x = 123 } = {}; // 123
```

```js
// ❌ instead of 💩
const [x, ...y] = ["a", "b", "c"]; // x='a'; y=['b', 'c']

// better do ✅
const [x, ...[y, z]] = ["a", "b", "c"]; // x = 'a'; y = 'b'; z = 'c'
```

```js
// ❌ instead of 💩
let y;
if (someValue.prop === undefined) {
  y = someFunc();
} else {
  y = someValue.prop;
}

// better do ✅
const { prop: y = someFunc() } = someValue;
```

---

## Reading Values With Array and assigning From Array to Local Variables

> We typically access array elements by their index, but doing so for more than just a couple of elements can quickly turn into a repetitive task.
better do: Reading Values With Array Destructuring. We can use destructuring to assign multiple values from an array to local variables.

```js
// ❌ instead of 💩
let users = ["Leo", "and", "Carley"];
let a = users[0];
let b = users[1];
let c = users[2];

// better do ✅

let users = ["Leo", "and", "Carley"];
let [a, b, c] = users;
console.log(a, b, c);
```

- Combining Destructuring With Rest Params

```js
// or even better
let users = ["Leo", "and", "Carley"];
let [first, ...rest] = users; // groups remaining arguments in an array
console.log(first, rest); // Leo ["and", "Carley"]
```

---

## rest function parameters

```js
function foo(...[a, b, c]) {
  console.log(...[a, b, c]);
  return a + b + c;
}
foo(1, 2, 3); // 6
foo(1, 2, 3, 4); // 6 (the fourth parameter is not Destructuringd)
```

---

## Rename Things Using Destructuring Aliases

```js
import { some-func1, some-func2 } from 'some-library';
//use aliasing
import { some-func1 as newFunc } from 'some-library';
newFunc();
import { * as some-library } from 'some-library'
```

---

## Omitting Properties Using the Rest Syntax

```js
const arr = ["Hello", "How", "are", "you"];
var [hello, ...remaining] = arr;

console.log(remaining); // ["How" , "are", "you"]
```

---

## Bind properties to variables

```js
const heroes = [{ name: "Batman" }, { name: "Joker" }];

for (const { name } of heroes) {
  console.log(name); // 'Batman', 'Joker'
}
```

---

## Function composition

it is the act of combining simple functions to build more complicated ones.

We can Applying Function Composition to Components

Functional composition is a mechanism to build complex functions by combining multiple simpler functions (Web Components).

This style can help you create more reusable functions in your code, reducing duplication, testing, and bugs.

> Favor `function composition` instead `encapsulation`

Ej1)

```js
// This one function is trying to do too much
// instrad of
function complexFunction(x) {
  const a = 2 _ x;
  const b = a + 5;
  const c = b / 2;
  const d = c _ 12;
  return d;
}

// better do ✅: use function composition
// We can achieve the same behaviour using compose instead:
// Here we have broken out the various math operations into pure functions
function add(r, x) { return x + r; }
function multiply(r, x) { return x *; }
function divideBy(r, x) { return x / r; }
const complexFunction = compose(
  multiply(12),
  divideBy(2),
  compose( add(5), multiply(2) )
);
```

- Result:
  Instead of having one massive function which accounts for various scenarios
  we have created a toolbox of smaller single responsibility functions.
  Testing this is much easier because you don't have to account for the different scenarios.

Ej2)

```js
var sine = (x) => Math.sin(x);
cube = (x) => x _ x _ x;
compose = (f, g) => (x) => f(g(x));
compose(sine, cube)(2); // 0.9893582466233818
```



```js
// sum(3)(4)(5)=12
function sum(a) {
  return function (b) {
    return function (c) {
      return a + b + c;
    };
  };
}
```

```js
// 2
function sum(a) {
  return (b) => (c) => a + b + c;
}
sum(3)(4)(5);
```

```js
// 3
// in this case we stuck on 3 parameters
let add = (a, b, c) => a + b + c;
console.log(add(3, 4, 5));
```

```js
function coordinate(lat, long) {
  let _lat = lat;
  let _long = long;
  return {
    latitude: function () {
      return _lat;
    },
    longitude: function () {
      return _long;
    },
    translate: function (dx, dy) {
      return coordinate(_lat + dx, _long + dy);
    },
    toString: function () {
      return "(" + _lat + "," + _long + ")";
    },
  };
}

module.exports = {
  coordinate: coordinate,
};

coordinate(12, 12).latitude(); // 12
```

Ej1)

```js
// This one function is trying to do too much
function complexFunction(x) {
  const a = 2 _ x;
  const b = a + 5;
  const c = b / 2;
  const d = c _ 12;
  return d;
}
```

```js
// Better: use function composition
// We can achieve the same behaviour using compose instead:
// Here we have broken out the various math operations into pure functions
function add(r, x) {
  return x + r;
}
function multiply(r, x) {
  return x * r;
}
function divideBy(r, x) {
  return x / r;
}
const complexFunction = compose(
  multiply(12),
  divideBy(2),
  compose(add(5), multiply(2))
);
```

### Result

Instead of having one massive function which accounts for various scenarios we have created a toolbox of smaller single responsibility functions.
Testing this is much easier because you don't have to account for the different scenarios.

Ej2)

```js
var sine = (x) => Math.sin(x);
cube = (x) => x _ x _ x;
compose = (f, g) => (x) => f(g(x));
compose(sine, cube)(2); // 0.9893582466233818
```

---

### OOP Composition

> Don't confuse `Functional Composition` with `OOP Composition`

> Favor `composition` instead `inheritance`

> Composition is instantiating and accessing a class inside another instead of inheriting from it.

> Any inheritance relationship can be converted into composition.

> `Composition` should be favored above `inheritance` because it is more flexible and allows us to design loosely coupled applications: Instead of creating a child class that inherits functionality from a parent class, we create stand-alone classes that contain other classes.

```js
// Object Composition
class Class_1 {
  method() {}
}

class Class_2 {
  class_1_object_name;

  constructor() {
    // create object of Class_1
    this.class_1_object_name = new Class_1();
  }
}
var class_2_obj = new Class_2();

class_2_obj.class_1_obj.method();
```

It's similar to how we construct properties, except this time we create a new instance object of another class.

```js
class CanJump {
  sendMessage() {
    console.log("Action jump");
  }
}

class DoAction {
  push;

  constructor() {
    this.push = new CanJump();
  }

  triggerAction() {
    console.log("triggeting action");
    return true;
  }
}
var test = new DoAction();
test.triggerAction(); // triggeting action
test.push.sendMessage(); // Action jump
```

The `DoAction` Class now has access to the functionality to `sendMessage()` without inheriting from the `CanJump` class.

---

## Typescript Mixins

### Multiple Inheritance with TypeScript Mixins

Imagine that instead of having a hierarchy of classes, you instead have a number of very small partial classes. These classes can be combined together and build larger classes with great flexibility.

```js
function pinMixin(BaseClass) {
  return class extends BaseClass {
    pin() {
      // implementation
    }
  };
}
function closeMixin(BaseClass) {
  return class extends BaseClass {
    close() {
      // implementation
    }
  };
}
```

We create a Base class that is created by merging the mixins functions, and then we extend the implementation:

```js
const BaseTabMixin = pinMixin(closeMixin(class {}));
class Tab extends BaseTabMixin {}
// Tab now can use the methods `close` and `pin`
```

Interfaces are very flexible, `we can inherit "Interfaces" from different interfaces and classes whatever way we want, unlike classes`.

> Interfaces can have multiple inheritance to inherit all the members. Each of these classes or interfaces is called a mixin, but Classes cannot: Classes can only extend a single class

```js
class Animal {
  species: string;
  constructor(species: string) {
    this.species = species;
  }
}
class Person {
  name: string;
  constructor(name: string) {
    this.name = name;
  }
}
interface Employee extends Person, Animal {
  employeeCode: string;
}
let employee: Employee = {
  species: "human",
  name: "Joe",
  employeeCode: "123",
};
```

But if we try to inherit from multiple classes:

```js
class Animal {
    species: string;
    constructor(species: string) {
        this.species = species
    }
}
class Person {
    name: string;
    constructor(name: string) {
        this.name = name
    }
}
class Employee extends Person, Animal {
    // It won't work if we use it in a class.
    employeeCode: string;
}
let employee: Employee = {
    species: 'human',
    name: 'Joe',
    employeeCode: '123'
}
// ERROR: Classes can only extend a single class.(1174)
```

- LINKS
  https://blog.bitsrc.io/composing-angular-components-with-typescript-mixins-31e3833560f7?gi=2eb2c70aa8a
  https://blog.bitsrc.io/component-inheritance-in-angular-acd1215d5dd8
  https://codeburst.io/multiple-inheritance-with-typescript-mixins-d92d01198907

---

### remove an string from array of strings

```js
const array = ["A", "B", "C", "D"];
const item = "C";

array.filter((x) => x !== item); // ["A", "B", "D"]
```

---

### remove array of string from another array of strings

```js
const array = ["A", "B", "C", "D"];
const item = ["A", "B"];

array.filter((el) => !item.includes(el)); // ["C", "D"]
```

---

### is Array element Contained In Array 2. utility

Returns true if the elements of the first array are contained in the second one regardless of order, false otherwise.

```js
const isArray1ContainedInArray2 = (a, b) => {
  for (const v of new Set(a)) {
    if (
      !b.some((e) => e === v) ||
      a.filter((e) => e === v).length > b.filter((e) => e === v).length
    )
      return false;
  }
  return true;
};

isArray1ContainedInArray2([1, 4], [2, 4, 1]); // true
```

---

### Generic Function to Update and Manipulate Object Arrays

// Updates an object array at the specified update key with the update value,
// if the specified test key matches the test value.
// Optionally pass 'testFailValue' to set a default value if the test fails.

```js
export const updateArray = <T, U extends keyof T, V extends keyof T>(params: {
    array: Array<T>
    testKey: keyof T
    testValue: T[U]
    updateKey: keyof T
    updateValue: T[V]
    testFailValue?: T[V]
}): Array<T> => {
const {
    array,
    testKey,
    testValue,
    updateKey,
    updateValue,
    testFailValue,
} = params
return array.map(item => {
      if (item[testKey] === testValue) {
          item[updateKey] = updateValue
      } else if (testFailValue !== undefined) {
          item[updateKey] = testFailValue
      }
      return item
    })
}

// use it
const onChangeCode = (code: string) => {
    setEditorSettingsState(updateArray({
        array: editorSettingsState,
        testKey: "isActive",
        testValue: true,
        updateKey: "code",
        updateValue: code,
    }))
}
```

---

### Filter / reduce .Array based on another array values

```js
const hashParamsCurrentMYOSelection = [
  "path=setting",
  "step=ring_size",
  "selection.design_setting=5606",
  "selection.design_style=5605",
  "selection.metal=5460",
  "selection.gem_shape=5537",
  "selection.gem_carat.min=0.3",
  "selection.gem_carat.max=0.5",
  "selection.gem_colour=5548",
  "selection.gem_clarity=5552",
  "selection.gem_cut=5560",
  "selection.gem=42762",
  "selection.ring_size=148967",
];

var hashParamsCurrentMYOSelectionFilteredNoClarity =
  hashParamsCurrentMYOSelection.filter((value, index, arr) => {
    return value.substring(0, 21) !== "selection.gem_clarity".substring(0, 21);
  });
var hashParamsCurrentMYOSelectionFilteredNoColour =
  hashParamsCurrentMYOSelection.filter((value, index, arr) => {
    return value.substring(0, 21) !== "selection.gem_colour".substring(0, 20);
  });
var hashParamsCurrentMYOSelectionFilteredNoCut =
  hashParamsCurrentMYOSelection.filter((value, index, arr) => {
    return value.substring(0, 21) !== "selection.gem_cut".substring(0, 17);
  });

// new clone but without: ["selection.gem_clarity=5552"]
hashParamsCurrentMYOSelectionFilteredNoClarity; // ["path=setting", "step=ring_size", "selection.design_setting=5606", "selection.design_style=5605", "selection.metal=5460", "selection.gem_shape=5537", "selection.gem_carat.min=0.3", "selection.gem_carat.max=0.5", "selection.gem_colour=5548", "selection.gem_cut=5560", "selection.gem=42762", "selection.ring_size=148967"]

hashParamsCurrentMYOSelectionFilteredNoColour; // ["path=setting", "step=ring_size", "selection.design_setting=5606", "selection.design_style=5605", "selection.metal=5460", "selection.gem_shape=5537", "selection.gem_carat.min=0.3", "selection.gem_carat.max=0.5", "selection.gem_colour=5548", "selection.gem_clarity=5552", "selection.gem_cut=5560", "selection.gem=42762", "selection.ring_size=148967"]

hashParamsCurrentMYOSelectionFilteredNoColour; // ["path=setting", "step=ring_size", "selection.design_setting=5606", "selection.design_style=5605", "selection.metal=5460", "selection.gem_shape=5537", "selection.gem_carat.min=0.3", "selection.gem_carat.max=0.5", "selection.gem_colour=5548", "selection.gem_clarity=5552", "selection.gem_cut=5560", "selection.gem=42762", "selection.ring_size=148967"]
```

---

### Split array into smaller ammounts

```js
const chunk = (arr, size) =>
  Array.from(
    {
      length: Math.ceil(arr.length / size),
    },
    (v, i) => arr.slice(i * size, i * size + size)
  );

// chunk array into smaller arrays of size 2
const chunks = chunk([1, 2, 3, 4, 5, 6], 2); // [1,2], [3,4], [5,6]
```

---

## concatenate the user names in order to display them

```js
const users = [
  { firstName: "Leo", lastName: "Lanese" },
  { firstName: "Carley", lastName: "Lanese" },
];

const result = users.map((item) => {
  return [item.firstName, item.lastName].join(" ");
});

result; // ["Leo Lanese", "Carley Lanese"]
```

---

### get the first match array element. MB

Use `Array.find()` to get the first match array element. If no result found `Array.find()` returns undefined. You can use `||` to set a default value.

```js
const people = [
  { id: 1, name: "Ted" },
  { id: 2, name: "Marshall" },
  { id: 3, name: "Barney" },
];

const getNameByID = (id) =>
  (people.find((o) => o.id === id) || { name: null }).name;

console.log(getNameByID(1));
console.log(getNameByID(50));
```


```js
const data = [3, 4];

// Same as for (let k in data) console.log(k)
Object.keys(data).forEach((k) => console.log(k)); // 0 1
```

```js
const data = [3, 4];

// Iterate over the values
Object.values(data).forEach((v) => console.log(v)); // 3 4
```

```js
const data = [3, 4];

// Iterate over the data, returning key-value pairs
Object.entries(data).forEach((e) => console.log(e[0], e[1])); // [0, 3] [1, 4]
```

---

### find function

```js
const members = [
{gender: 'M', name: 'John'},
{gender: 'M', name: 'Tim'},
{gender: 'F', name: 'Jenny'},
{gender: 'F', name: 'Alice'}
]

member = members.find(member => member.gender === 'M' && member.name === 'Tim');
// {gender: 'M', name: 'Tim'}
```

---

### Possible permutations of a number

```js
const permutations = (arr) => {
  if (arr.length <= 2) return arr.length === 2 ? [arr, [arr[1], arr[0]]] : arr;
  return arr.reduce(
    (acc, item, i) =>
      acc.concat(
        permutations([...arr.slice(0, i), ...arr.slice(i + 1)]).map((val) => [
          item,
          ...val,
        ])
      ),
    []
  );
};

permutations([1, 33, 5]); // [ [1, 33, 5], [1, 5, 33], [33, 1, 5], [33, 5, 1], [5, 1, 33], [5, 33, 1] ]
```

---

### adding value to every element in the array

```js
const files = ["foo.txt ", ".bar", "   ", "baz.foo"];
const filePaths = files
  .map((file) => file.trim())
  .filter(Boolean)
  .map((fileName) => `~/cool_app/${fileName}`);

// filePaths = [ '~/cool_app/foo.txt', '~/cool_app/.bar', '~/cool_app/baz.foo']
```

---

### Filter null from an array

```js
[1, "", null, NaN, 2, undefined, 4, 5, 6].filter((x) => !!x); // 1, 2, 4, 5, 6
```

---

### Separate/split elements inside array of string using `flatMap`

```js
const family = ["Leo, Tom", "Carley, Sam"];

family.flatMap((x) => x.split(",")); //  ["Leo", " Tom", "Carley", " Sam"]
```

---



### `get property` selected `by id` from Array of Objects

```js
const sales = [
  { product: "iPhone", price: 999, sales: 45, id: 0 },
  { product: "S10", price: 999, sales: 45, id: 1 },
  { product: "Ipad", price: 999, sales: 45, id: 2 },
];
const getSalebyId = (id) =>
  (sales.find((x) => x.id === id) || { product: null }).product;

console.log(getSalebyId(1)); // S10
console.log(getSalebyId(2)); // Ipad
```

---

### get `Total` sum from `Array`

```js
const arr = [10, 20, 30, 40];

arr.reduce((x, y) => x + y); // 100
```

---

### get `Total` sum from `Array of Object`

```js
const sales = [
  { product: "Phone", price: 999, sales: 45 },
  { product: "Phone", price: 999, sales: 45 },
  { product: "Phone", price: 999, sales: 45 },
];

let revenue = sales.reduce((total, currentValue) => {
  return total + currentValue.price * currentValue.sales;
}, 0);

console.log("Total: $", revenue); // Total: $ 134865
```

---

### get Total sum from Array of Object

```js
const pilots = [
  {
    id: 10,
    name: "Poe Dameron",
    years: 14,
  },
  {
    id: 2,
    name: "Temmin 'Snap' Wexley",
    years: 30,
  },
  {
    id: 41,
    name: "Tallissan Lintra",
    years: 16,
  },
  {
    id: 99,
    name: "Ello Asty",
    years: 22,
  },
];

totalYears = pilots.reduce((acc, pilot) => acc + pilot.years, 0); // 82
```

---

### Condition object properties: get values out of the

```js
const getName = (hasEmail) => ({
  name: "Leo",
  age: 40,
  ...(hasEmail && { email: "developer@leolanese.com" }),
});

console.log(getName(false)); // {name: "Leo", age: 40}
console.log(getName(true)); // {name: "Leo", age: 40, email: "developer@leolanese.com"}
```

```js
const getName = (hasName, hasAge, hasEmail) => ({
  ...(hasName && { name: "Leo" }),
  ...(hasAge && { age: 40 }),
  ...(hasEmail && { email: "developer@leolanese.com" }),
});

console.log(getName(1)); // {name: "Leo"}
console.log(getName(1, 1)); // {name: "Leo", age: 40}
console.log(getName(1, 1, 1)); // {name: "Leo", age: 40, email: "developer@leolanese.com"}
```

```js
const getName = (arr, hasName, hasAge, hasEmail) => ({
  ...(hasName && arr[0]),
});

const arr = [{ name: "Leo", age: 40, email: "developer@leolanese.com" }];
console.log(getName(arr, 1)); // {name: "Leo", age: 40, email: "developer@leolanese.com"}
```

---

### Take max value from Array of Object

```js
const pilots = [
  {
    id: 10,
    name: "Poe Dameron",
    years: 14,
  },
  {
    id: 2,
    name: "Temmin 'Snap' Wexley",
    years: 30,
  },
  {
    id: 41,
    name: "Tallissan Lintra",
    years: 16,
  },
  {
    id: 99,
    name: "Ello Asty",
    years: 22,
  },
];

mostExpPilot = pilots.reduce((oldest, pilot) => {
  return (oldest.years || 0) > pilot.years ? oldest : pilot;
}, {}); // {id: 2, name: "Temmin 'Snap' Wexley", years: 30}
```

---

### Comparing different Array of Objects specific positions

```js
const trackBy = (_, item) => item.id;

const a = [
  { id: 1, name: "Leo" },
  { id: 2, name: "Carley" },
  { id: 3, name: "Tom" },
];

const b = [
  { id: 1, name: "Leo" },
  { id: 2, name: "Sam" },
  { id: 4, name: "Tom" },
];

console.log(trackBy(0, a[0]), trackBy(0, b[0])); // 1 1 = identical
console.log(trackBy(1, a[1]), trackBy(1, b[1])); // 2 2 = identical
console.log(trackBy(2, a[2]), trackBy(2, b[2])); // 3 4 = NOT identical
```

---

### Simple rest arguments

```js
const fn = (...args) => console.log(args);

fn(1, 2, 3); // [1, 2, 3]
fn("one", "two"); // ['one', 'two']
```

---

### Take array, get the number elements, multiply those by 2

```js
// ❌ instead of 💩
var arr = ["This", "is", null, null, 0, true, , NaN, -1, "javaScript", 1];

arr.filter((a) => typeof a === "number").map((x) => x * 2); // [0, NaN, -2, 2]

// better do ✅
const arr = ["This", "is", null, null, 0, true, , NaN, -1, "javaScript", 1];
const calc = (x) => (x) => x * 2;

arr.filter((a) => typeof a === "number").map(calc()); // [0, NaN, -2, 2]
```

---

### `Merge 2 arrays`. Utility

```js
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [6, 7, 8, 9, 10];

const arrX = [arr1, arr2];
arrX.flat(); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

---

### filter array based on number

```js
[1, 2, 3, 4, 5].filter((a) => a <= 2); // [1, 2]

[1, 2, 3, 4, 5].filter((a) => a > 2); // [3, 4, 5]
```

---

### returns minimum (min) element in the Array of Objects. utility

```js
const reduceWhich = <T extends number | string | AnyObject = number>(
  arr: T[],
  comparator: Function = (a: number, b: number) => (a - b) as number
) => arr.reduce((a: T, b: T) => (comparator(a, b) >= 0 ? b : a));

reduceWhich([1, 3, 2]); // 1
reduceWhich([1, 3, 2], (a, b) => b - a); // 3
reduceWhich(
  [
    { name: "Tom", age: 12 },
    { name: "Jack", age: 18 },
    { name: "Lucy", age: 9 },
  ],
  (a, b) => a.age - b.age
); // {name: "Lucy", age: 9}
```

---

### scrollToTop

```js
const scrollToTop = () => {
  const c = document.documentElement.scrollTop || document.body.scrollTop;
  if (c > 0) {
    window.requestAnimationFrame(scrollToTop);
    window.scrollTo(0, c - c / 8);
  }
};

scrollToTop();
```

---

### bottom page visible

> Returns true if the bottom of the page is visible, false otherwise. Utility.

```js
const bottomVisible = () =>
  document.documentElement.clientHeight + window.scrollY >=
  (document.documentElement.scrollHeight ||
    document.documentElement.clientHeight);

bottomVisible(); // true
```

### scroll Y position

```js
const getScrollPosition = (el = window) => ({
  x: el.pageXOffset !== undefined ? el.pageXOffset : el.scrollLeft,
  y: el.pageYOffset !== undefined ? el.pageYOffset : el.scrollTop,
});

getScrollPosition(); // {x: 0, y: 200}
```

---

### smoothScroll

Smoothly scrolls the element on which it's called into the visible area of the browser window.

```js
const smoothScroll = (element) =>
  document.querySelector(element).scrollIntoView({
    behavior: "smooth",
  });

smoothScroll("#fooBar"); // scrolls smoothly to the element with the id fooBar
smoothScroll(".fooBar"); // scrolls smoothly to the first element with a class of fooBar
```

---

### Returns the first defined, non-null argument

```js
const coalesce = (...args) => args.find((v) => ![undefined, null].includes(v));

coalesce(null, undefined, "", NaN, "Waldo"); // ''
```

---

### Filter an Array of Objects based on a condition while also filtering out unspecified keys. utility

```js
const reducedFilter = (data, keys, fn) =>
  data.filter(fn).map((el) =>
    keys.reduce((acc, key) => {
      acc[key] = el[key];
      return acc;
    }, {})
  );
const data = [
  {
    id: 1,
    name: "john",
    age: 24,
  },
  {
    id: 2,
    name: "mike",
    age: 50,
  },
];

reducedFilter(data, ["id", "name"], (item) => item.age > 24);
// [{ id: 2, name: 'mike'}]
```

---

## highest number inside Array of Objects

```js
let employees = [
  {
    id: 11,
    name: "Abhinav",
    salary: 75000,
  },
  {
    id: 2131,
    name: "Gaurav",
    salary: 62000,
  },
  {
    id: 3012,
    name: "Raj",
    salary: 32000,
  },
];

employees.reduce(
  (a, employee) => ((a.salary || 0) > employee.salary ? a : employee),
  {}
); // {id: 11, name: "Abhinav", salary: 75000}
```

---

### merge / combine of two or more objects. utility

```js
const merge = (...objs: AnyObject[]) =>
  [...objs].reduce(
    (acc, obj) =>
      Object.keys(obj).reduce((a, k) => {
        acc[k] = acc.hasOwnProperty(k)
          ? [].concat(acc[k]).concat(obj[k])
          : obj[k];
        return acc;
      }, {}),
    {}
  );

const object = {
  a: [{ x: 2 }, { y: 4 }],
  b: 1,
};
const other = {
  a: { z: 3 },
  b: [2, 3],
  c: "foo",
};
merge(object, other); // { a: [ { x: 2 }, { y: 4 }, { z: 3 } ], b: [ 1, 2, 3 ], c: 'foo' }
```

---

### check if a property exists in object: `in`

```js
const person = { firstName: "Dave", surname: "Smith", age: 34 };

"firstName" in person; // returns true
"surname" in person; // returns true
"age" in person; // returns true
"gendar" in person; // returns false
```

---

### Sort Array of Objects by Property Values

```js
// program to sort array by property name
function compareAge(a, b) {
  return a.age - b.age;
}
let students = [
  { name: "Sara", age: 24 },
  { name: "John", age: 22 },
  { name: "Jack", age: 27 },
];

console.log(students.sort(compareAge));
// [{name: "John", age: 22},{name: "Sara", age: 24},{name: "Jack", age: 27}]
```

---

### Check check if a key exists in Object

```js
let person = {id: 1,name: 'John',age: 23}

let hasKey = 'name' in person;

hasKey
  ? console.log('The key exists.')
  : console.log('The key does not exist.'); // The key exists
```

---


### compare arrays equality

```js
const oldTags = ["facebook","twitter","instagram","dev.to"];
const newTags = ["dev.to","twitter","facebook","instagram"];
                               
// Method1 : Using .sort()&.join()
const arr1 = oldTags.sort().join();
const arr2 = newTags.sort().join();
console.log("isEqual?",arr1 === arr2);
```

```js
// Method2 : Using includes()
let arr1Status = true;
oldTags.forEach((value)=>{
  arriStatus=arr1Status && newTags.includes(value);
});

let arr2Status=true;
newTags.forEach((value)=>{
 arr2Status=arr2Status && oldTags.includes(value);
});
console.log("isEqual?",arr1Status && arr2Status);
```

```js
// Method3 : Using .reduce()
let arr1State=oldTags.reduce(
  (acc,value)=>acc && newTags.includes(value),
 true
);
let arr2State=newTags.reduce(
  (acc,value)=>acc && oldTags.includes(value),
  true
);
console.log("isEqual?",arr1State && arr2State);
```

```js
// Method4 : Using .isEqual()from Lodash
console.log("isEqual?",_.isEqual(oldTags.sort(),newTags.sort()));
```


---
### compare arrays and return differences: symmetric difference

```js
// return elements from tab1 that don't exist
// on tab2 and elements from tab2
// that don't exist on tab1
const tab1 = [1, 2, 3, 12, 4, 5, "A"];
const tab2 = [1, 2, 78, 3, 189];

const arrayDifference = (tab1, tab2) => [
  ...tab1.filter((item) => findItem(tab2, item).length === 0),
  ...tab2.filter((item) => findItem(tab1, item).length === 0),
];
console.log("Differences : ", arrayDifference(tab1, tab2)); // [ 12, 4, 5, 'A', 78, 189 ]
```

---

### Replace the description value on to "DATA.country" field for the "REF.description"

```js
REF = [
  {
    country: "UK",
    description: "United Kingdom",
  },
  {
    country: "USA",
    description: "United States Of America",
  },
];

arr = REF.map((a) => a.description); // ["United Kingdom", "United States Of America"]

DATA = [
  {
    name: "AAA",
    place: "London",
    country: "UK",
  },
  {
    name: "BBB",
    place: "NewYork",
    country: "USA",
  },
];
reformattedArray = DATA.map(function (obj) {
  obj.country === "UK" ? (obj.country = arr[0]) : (obj.country = arr[1]);
  return obj;
});
```

---

### Deep difference between array of objects.

```js
// deep nested array of objects
const tabObject1 = [
  {
    name: "Leo",
    lastName: "Lanese",
  },
  {
    name: "Steve",
    lastName: "Jobs",
  },
  {
    name: "Pablo",
    lastName: "Picasso",
  },
];

const tabObject2 = [
  {
    name: "Tom",
    lastName: "Lanese",
    note: 14,
  },
  {
    name: "Dan",
    lastName: "Abramov",
    note: 17,
  },
  {
    name: "Steve",
    lastName: "Jobs",
    note: 16,
  },
  {
    name: "Albert",
    lastName: "Einsten",
    note: 18,
  },
];
```

### deep arrays difference

```js
// deep find item
const deepFindItem = (tab, query) => tab.filter(item => item.name === query.name)

// 1. find tab1 difference
// 2. find tab2 difference
const deepArrayDifference = (tab1, tab2) => [
 ...tab1.filter(item => deepFindItem(tab2, item).length === 0),
 ...tab2.filter(item => deepFindItem(tab1, item).length === 0),
]

deepArrayDifference(tabObject1, tabObject2)); // [{name: 'Pablo', lastName: 'Picasso'}, {name: 'Albert', lastName: 'Einsten'}, {name: 'Dan', lastName: 'Abramov'}]
```

---

### Perform Intersection using filter() method

```js
// eg1
let array1 = [1, 2, 3, 5, 9];
let array2 = [1, 3, 5, 8];

array1.filter((x) => array2.includes(x)); // [1, 3, 5]
```

```js
// eg2
let array1 = [1, 2, 3, 5, 9];
let array2 = [1, 3, 5, 8];

// program to perform intersection between two arrays
function performIntersection(arr1, arr2) {
  return arr1.filter((x) => arr2.indexOf(x) !== -1);
}

performIntersection(array1, array2); // [1, 3, 5]
```

---

### deep array similareties. Intersection

```js
// find common elements
const tab1 = [1, 2, 3, 12, 4, 5, "A"];
const tab2 = [1, 2, 78, 3, 189];

const deepArrayIntersection = (tab1, tab2) =>
  tab1.filter((item) => deepFindItem(tab2, item).length > 0);

console.log(
  "Deep Intersection : ",
  deepArrayIntersection(tabObject1, tabObject2)
); // {lastName: "Jobs", name: "Steve"}
```

---
### Conditionally add property to an object

```js
const moreInfos = { info: "Please go to the desk." }
return {
  address: "20B Rue Lafayette",
  postcode: "75009",
  ...(moreInfos !== undefined && { moreInfos })
}
```

---
### add value to the end of array

```js
const tab4 = ["a", "b", "c"];

tab3.push(...tab4); // [ 1, 2, 3, 4, 5, 7, 8, 9, 10, 11, 'a', 'b', 'c' ];
```

---

### add array at the begin of the array

```js
const tab1 = ["A", "B", "C"];
const tab2 = [1, 2, 3];
tab2(...tab1);

console.log(tab2); // ["A", "B", "C", 1, 2, 3]
```

---

### combine/concat arrays do not duplicates. Union. Utility

```js
const tab1 = [1, 2, 3, 4, 5];
const tab2 = [1, 5, 7, 8, 9, 10, 11];

// union maintaining duplications
const tab3 = [...tab1, ...tab2]; // [1, 2, 3, 4, 5, 1, 5, 7, 8, 9, 10, 11]
```

```js
const arrA = [1, 2, 3, 4, 5, 11];
const arrB = [7, 8, 9, 10, 11, 1];

// using removing duplications
[...new Set([...arrA, ...arrB])]; // [1, 2, 3, 4, 5, 11, 7, 8, 9, 10]
```

---

### union arrays and eliminate duplication. Union. Utility

```js
const tab1 = [1, 2, 3, 4, 5];
const tab2 = [7, 8, 9, 10, 11];

// Union: merge arrays and eliminate duplication
const arrayUnionNoDuplication = (a: any[], b: any[]) =>
  Array.from(new Set([...a, ...b]));

arrayUnionNoDuplication(tab1, tab2); // [ 1, 2, 3, 5, 7, 8, 9, 10, 11]
```

---

### Returns unique values of array, based on a provided comparator function. Utility

```js
const uniqueBy = (arr: any[], fn: Predicate) =>
  arr.reduce((acc, v) => {
    if (!acc.some((x: any) => fn(v, x))) acc.push(v);
    return acc;
  }, []);

uniqueBy(
  [
    { id: 0, value: "a" },
    { id: 1, value: "b" },
    { id: 2, value: "c" },
    { id: 1, value: "d" },
    { id: 0, value: "e" },
  ],
  (a: any, b: any) => a.id == b.id
); // [{id: 0, value: 'a'}, {id: 1, value: 'b'}, {id: 2, value: 'c'}]
```

---

### replace value matching of a string. replaceAll ES11

```js
"x".replace("", "_");
// → '_x'

"xxx".replace(/(?:)/g, "_");
// → '_x_x_x_'

"xxx".replaceAll("", "_");
// → '_x_x_x_'
```

```js
// ❌ instead of 💩
function replaceAll(str, find, replace) {
  return str.replace(new RegExp(escapeRegExp(find), "g"), replace);
}
function escapeRegExp(string) {
  return string.replace(/[.*+\-?^${}()|[\]\\]/g, "\\$&"); // $& means the whole matched string
}

replaceAll("hola mundo", "hola", "hello"); // "hello mundo"

// better do ✅
"hola mundo".replaceAll("hola", "hello"); // "hello mundo"
```

```js
// eg2
const fullname = "fullname=Jhon+Hannibal+Smith";

const fullnameFormated = fullname.replaceAll("+", " "); // Jhon Hannibal Smith
```

```js
// eg3
inputString = "es2021 first sample code first";

console.log(inputString.replaceAll(/first/g, "")); // es2021  sample code
console.log(inputString.replace(/first/g, "")); // es2021  sample code
```

---

### deep union. Union. Utility . MB

```js
// 1. find common elements tab1 & tab2
// 2. find tab1 difference
// 3. find tab2 difference
// 4. merge result
// intersection + difference
// intersection is like a Set()
// to eliminate duplicated elements
const deepArrayUnion = (tab1, tab2) => [
  ...deepArrayIntersection(tab1, tab2),
  ...deepArrayDifference(tab1, tab2),
];
console.log("Deep Union : ", deepArrayUnion(tabObject1, tabObject2));
// [ { name: 'Héla', lastName: 'Ben Khalfallah' },
// { name: 'Steve', lastName: 'Jobs' },
// { name: 'Pablo', lastName: 'Picasso' },
// { name: 'Albert', lastName: 'Einsten' },
// { name: 'Dan', lastName: 'Abramov' } ]
```

---

### Using Array reduce to safely access nested objects. Deep validation. Utility.

```js
// deep nested object to be inspected
const user = {
  personalInfo: {
    name: "Leo Lanese",
    addresses: [{ city: "Rosario" }],
  },
};

// utility
const getNestedObject = (nestedObj, pathArr) => {
  return pathArr.reduce(
    (obj, key) => (obj && obj[key] !== "undefined" ? obj[key] : null),
    nestedObj
  );
};

// pass in your object structure as array of strings
const name = getNestedObject(user, ["personalInfo", "name"]); // 'Leo Lanese'

// to access nested array, just pass in array index as an element the path array.
// this will return the city from the first address item.
const city = getNestedObject(user, ["personalInfo", "addresses", 0, "city"]);
```

```js
// alternativly `.?`
user?.personalInfo?.name; // 'Leo Lanese'
user?.personalInfo?.addresses[0].city; // Rosario
```

---

### sum all values of array of integers

```js
[1, 2, 3].reduce((acc, cur) => acc + cur, 0); // 6
```

---

### check all values are true the array of booleans

```js
[true, false, true].reduce((acc, cur) => acc && cur, true); // false
```

---

### Check if the object has a nested value

```js
// nested object to explore
const obj = {
  mainItems: {
    superItems: [59, 3554, 54, 87123],
    loading: false,
  },
  otherItems: {
    targetItem: "You looking for me?",
  },
};

// clone of the nested obj
const cloneObj = { ...obj, otherItems: {} };

function getDataNew(pathsArray, objectToLookFor) {
  let data = objectToLookFor;
  let path;
  for (let i = 0; i < pathsArray.length; i++) {
    if (data == null) {
      return;
    }
    path = pathsArray[i];
    data = data[path];
  }
  return data || false;
}

console.log(getDataNew(["otherItems", "targetItem"], obj)); // ok
console.log(getDataNew(["otherItems", "targetItem"], cloneObj)); // false
console.log(getDataNew(["otherItems", "wrongPath"], obj)); // false
```

---

### Filter odd numbers

```js
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let even = numbers.filter((num) => !Math.abs(num % 2));

console.log(even); // [2, 4, 6, 8, 10]
```

---

### max value from array of numbers

```js
console.log([0, 3, 1, 4, null, ""].reduce((acc, cur) => Math.max(acc, cur), 0)); // 4
```

---

### sum values of a property from an Array of Objects

```js
const data2 = [
  { val1: "abc", val2: 50 },
  { val1: "abc", val2: 50 },
  { val1: "cde", val2: 75 },
  { val1: "hji", val2: 35 },
  { val1: "bbc", val2: 25 },
];

console.log(data2.reduce((n, { val2 }) => n + val2, 0)); // 235
```

---

### Implementing map with reduce with no mutation:

```js
const mapExercise = (f, elements) =>
  elements.reduce((acc, curr) => {
    // reducer
    return [...acc, f(curr)]; // no-mutation
  }, []);
const arr = [0, 1, 2, 3, 4, 5, 6];

mapExercise((x) => x * x, arr); // [0, 1, 4, 9, 16, 25, 36]
```

---

### largest number from multiples arrays of arrays

```js
const arrObj = [
  [1, 2, 3, 4, 5],
  [-1, -2, -3, -4 - 5],
  [6, 7, 8, 9, 10],
  [-6, -7, -8, -9, -10],
];
function largestArray(arr) {
  return array.map((subArray) => Math.max(...subArray));
}

largestArray(arrObj); // [5, -1, 10, -6]
```

---

### calculate sum Total from Array of Objects

```js
let employees = [
  {
    id: 11,
    name: "Abhinav",
    salary: 75000,
  },
  {
    id: 2131,
    name: "Gaurav",
    salary: 62000,
  },
  {
    id: 3012,
    name: "Raj",
    salary: 32000,
  },
];
totalSalary = employees.reduce((a, employee) => {
  console.log(a, employee);
  return a + employee.salary;
}, 0);
// 0 {id: 11, name: "Abhinav", salary: 75000}
// 75000 {id: 2131, name: "Gaurav", salary: 62000}
// 62000 {id: 3012, name: "Raj", salary: 32000}
// 169000
```

---

### Get max object based on property from array of objects

```js
let employees = [
  {
    id: 11,
    name: "MrSmith",
    salary: 75000,
  },
  {
    id: 2131,
    name: "Lucciano",
    salary: 62000,
  },
  {
    id: 3012,
    name: "Maximo",
    salary: 32000,
  },
];
let employeeWithHighest = employees.reduce((a, employee) => {
  (a.salary || 0) > employee.salary ? a : employee;
}, {});
console.log(employeeWithHighest.name); // MrSmith
```

---

### get Multiples of number

```js
const multiplesOf = (numbers, number) => numbers.filter((n) => !(n % number));

console.log(multiplesOf([4, 5, 6, 7, 8], 2)); // [4, 6, 8]
```

---

### Take data from array of objects (deep nested object)

```js
const json = [
  {
    timestamp: "2019-01-15",
    purchases: [
      { product: "Product 1", total: 20, time: "09:00" },
      { product: "Product 1", total: 60, time: "12:00" },
    ],
  },
  {
    timestamp: "2019-01-16",
    purchases: [
      { product: "Product 1", total: 40, time: "10:00" },
      { product: "Product 2", total: 30, time: "11:00" },
    ],
  },
  {
    timestamp: "2019-01-17",
    purchases: [
      { product: "Product 1", total: 10, time: "14:00" },
      { product: "Product 2", total: 20, time: "17:00" },
    ],
  },
];

let product1Sales = json.flatMap(({ purchases }) => {
  return purchases
    .filter((sale) => sale.product === "Product 1")
    .map((sale) => sale.total);
}); // [20, 60, 40, 10]
```

---

### The first 3 words with NO numbers

```js
const myString = "Y0 test me L0L here please10 bye";

myString
  .split(" ") // ["Y0", "test", "me", "L0L", "here", "please10", "bye"]
  .filter((x) => !x.match(/[0-9]+/)) // ["test", "me", "here", "bye"]
  .slice(0, 3); //  ["test", "me", "here"]
```

---

### Order an Array and remove first element (without mutate)

```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];

const fruitsOrder = fruits.concat().sort(); // ["Apple", "Banana", "Mango", "Orange"]
const fruitsOrder.fruitsOrder.slice(1,10); // ["Banana", "Mango", "Orange"]
```

---
### capitalise string words

```js
const capitaliseWords = (str) =>
  str
    .split(" ")
    .map((word) => word.replace(word.charAt(0), word.charAt(0).toUpperCase()))
    .join(" ");
console.log("capitalise Words :", capitaliseWords("Argument goes here"));
// capitalise Words : Argument Goes Here
```

---

#### Square all odd (impar) numbers

```js
const arr = [1, 2, 3, 4, 5, 6];

arr
  .map((item) => (item % 2 === 0 ? item : item * item))
  .map((x) => console.log(x)); // [1, 2, 9, 4, 25, 6];
```

---

### modify/filter element from an array of objects

```js
let users = [
  { name: 'Leo', age: 20 },
  { name: 'Pepe', age: 25 },
]

let capitalNames = users.map(user => user.name }); // ["Leo", "Pepe"]
```

---

### modify/filter EACH element from an array of Objects

```js
let users = [
  { name: 'Leo', age: 20 },
  { name: 'Pepe', age: 25 }
]
let capitalNames = users.map(user => user.name.toLocaleUpperCase()}); // ["LEO", "PEPE"]
```

---

### modify/filter EACH element from an array of Objects

```js
let users = [
  { name: 'Leo', age: 20 },
  { name: 'Pepe', age: 25 }
]
let capitalNames = users.map(user => user.name.toLocaleUpperCase() + ' - age:' + user.age}); // ["LEO - age:20", "PEPE - age:25"]
```

---

### only accept enum Direction values as parameter

```js
const enum Direction {
 Up = "UP",
 Down = "DOWN",
 Left = "LEFT",
 Right = "RIGHT",
}
function move(where: Direction) { }

move("Down"); // will fail
move(Direction.Down); // only accept enum Direction values as parameter
```

---

### Average of Two Numbers or Array of numbers:

```js
const averageOfTwoNumbers = (...numbers) =>
  numbers.reduce((acc, current) => acc + current, 0) / numbers.length;

averageOfTwoNumbers(1, 2, 3); // 2
averageOfTwoNumbers(...[1, 2, 3]); // 2
```

```js
const average = (...numbers) => 
   numbers.reduce((num1, num2) => num1 + num2) / numbers.length;

average(1,2,3,4);// 2.5
```

```js
const average = (arr) => 
  arr.reduce((a, b) => a + b) / arr.length;

average([1,9,18,36]) //16
```
---

### Conditionally Add Property


```js
const age = 19;
const isPass = false ;

const student = {
  name: 'Steve',
  age: age,
  ...(age>=18 && {canVote: true})
  ...(isPass && {haveCertificate: true})
};

console.log('Student details: ', student); 
// {name:'Steve', age:19, canVote: true}
```

---

### Using magical blackbird (B1) combinator to make two calculations for the same input.

https://jrsinclair.com/articles/2019/compose-js-functions-multiple-parameters/

---

## take value or key based on any values - pluck MB

- LINKS
  [.pluck() - simple grab/emit specific key or value from object]
  (https://stackblitz.com/edit/typescript-rinjzk?file=index.ts&devtoolsheight=100)

[.combineLatest() - Gives lates values from arrays when observable emits]
(https://stackblitz.com/edit/typescript-ihcxud?file=index.ts&devtoolsheight=50)

[.scan() - Accumulating an object]
(https://stackblitz.com/edit/typescript-vu63kz?file=index.ts&devtoolsheight=100)

[.fromEvent() - Detect event and turn it into observable sequence (document, click)]
(https://stackblitz.com/edit/typescript-mfyefr?file=index.ts&devtoolsheight=50)

[using btns (getElementById)](https://stackblitz.com/edit/typescript-ihcxud?file=index.ts&devtoolsheight=50)

## validate all values in the array true

```js
import { every } from "rxjs/operators";
import { of, from } from "rxjs";

//emit 5 values
const val1 = true;
const val2 = true;
const val3 = [val1, val2];

const source = from(val3);
const example = source.pipe(
  //is every value true
  every((val) => val === true)
);
//output: false
const subscribe = example.subscribe((val) => console.log(val));
```

---

## grabbing only certain properties from an object & make another object with them - rxjs

https://stackblitz.com/edit/typescript-5qcvpo?file=index.ts

## make new object based on 1 array of objects + then only take certain keys and generate new object

https://stackblitz.com/edit/typescript-ae5u7e?file=index.ts

---

## create new Object from the Array of Object with the keys being "id"

```js
const sources = [
  {
    id: "idleo",
    url: "leo",
  },
  {
    id: "idtom",
    url: "tom",
  },
  {
    id: "Sam",
    url: "sam",
  },
];
sourcesMap = sources.reduce((map, source) => {
  map[source.id] = source; // id key for the new id
  return map;
}, {});

// {
//   "idleo": {"id":"idleo", "url":"leo"},
//   "idtom": {"id":"idtom", "url":"tom"},
//   "idsam": {"id":"idsam", "url":"sam"}
// }
```

// or with rxjs v6+

```js
import { from, of, zip } from "rxjs";
import { groupBy, mergeMap, toArray } from "rxjs/operators";

const sources = [{
    id: "idleo",
    url: "urlleo",
  },{
    id: "idtom",
    url: "urltom",
  },
];

from(sources)
  .pipe(
    groupBy(
      (n) => n.id,
      (p) => p.url
    ),
    mergeMap((group) => zip(of(group.key), group.pipe(toArray())))
  )
  .subscribe(console.log);
```

---

### Filter array of objects with multiple criteria / multiple Values

```js
function multiFilter(array, filters) {
  const filterKeys = Object.keys(filters);
  // filters all elements passing the criteria
  return array.filter((item) => {
    // dynamically validate all filter criteria
    return filterKeys.every((key) => {
      // ignores an empty filter
      if (!filters[key].length) return true;

      return filters[key].includes(item[key]);
    });
  });
}

const products = [
  { name: "A", color: "Blue", size: 50 },
  { name: "B", color: "Blue", size: 60 },
  { name: "D", color: "Black", size: 70 },
  { name: "D", color: "Green", size: 50 },
];

// the value of each key is an array with the values to filter
let filters = {
  color: ["Blue", "Green"],
  name: ["D"],
};

// filter the products array by color: blue and green and also by name D
multiFilter(products, filters); // {name: "D", color: "Green", size: 50}
```

---

### filter array of object by multiple entries

```js
// eg1
var firstQuery = [
  { name: "John", email: "johnson@mail.com", age: 25, address: "USA" },
  { name: "Tom", email: "tom@mail.com", age: 35, address: "England" },
  { name: "Mark", email: "mark@mail.com", age: 28, address: "England" }
];
var secondQuery = { address: "England", name: "Mark" };

firstQuery.filter(
  obj => obj.name == secondQuery.name && obj.address == secondQuery.address;
);   // {name: "Mark", email: "mark@mail.com", age: 28, address: "England"}
```

```js
// eg2
const person = [
  { name: "Leo 1", hear: "brown" },
  { name: "Leo 2", hear: "red" },
  { name: "Leo 3", hear: "blue" },
  { name: "Leo 4", hear: "green" },
];
person.filter(
  (currentvalue, currentIndex, array) => currentvalue.name === "Leo 1"
); // {name: "Leo 1", hear: "brown"}
```

---

### Search inside array of strings:

```js
const permissions = [
  "CASES_EDIT",
  "INBOUND_READ",
  "BULK_PROCESSING_EDIT",
  "HELD_QUEUE_CONTENT_VIEW",
  "SYSTEM_EDIT",
];

permissions.some(
  x => x === "BULK_DELIVERY_READ" || x === "BULK_DELIVERY_EDIT"
); // true
```

---

### Reformatting / change Array Objects

```js
const myUsers = [
  { name: "chuloo", likes: "grilled chicken" },
  { name: "chris", likes: "cold beer" },
  { name: "sam", likes: "fish biscuits" },
];

const usersByFood = myUsers.map((item) => {
  const container = {};
  container[item.name] = item.likes;
  container.age = item.name.length * 10;
  return container;
});

console.log(usersByFood);
// {chuloo: 'grilled chicken', age: 60}
// {chris: 'cold beer', age: 50}
// {sam: 'fish biscuits', age: 30}
```

---

### Given array of objects: output only those values that are more than a specified value X.

We no longer have to rely on for...in and hasOwnProperty now.
Filtering array of objects to filter the results when person.age > 21

```js
const people = [
  { name: "TK", age: 26 },
  { name: "Kaio", age: 10 },
  { name: "Kazumi", age: 30 },
];

/// old school IP for loops ways
for (i = 0; i < people.length; i++) {
  if (people[i].age > 21) {
    console.log(people[i]); // {name: "TK", age: 26} {name: "Kazumi", age: 30}
  }
}
```

```js
// a more declarative way
function olderThan21(person) {
  return person.age > 21;
}
function overAge(people) {
  return people.filter(olderThan21);
}

overAge(people); // [{ name: 'TK', age: 26 }, { name: 'Kazumi', age: 30 }]
```

---

### Search inside Array Object a value based on provided array of object

// Arrays are normally accessed via numeric indexes

```js
const arrObj = [
  {
    name: "xyz",
    grade: "x",
  },
  {
    name: "caca",
    grade: "x",
  },
  {
    name: "x",
    frade: "d",
  },
  {
    name: "a",
    grade: "b",
  },
];

function filterIt(arrObj, searchKey) {
  return arrObj.filter(function (obj) {
    return Object.keys(obj).some(function (key) {
      return obj[key].includes(searchKey);
    });
  });
}

filterIt(a, "a"); // {name: "caca", grade: "x"}, {name: "a", grade: "b"}
```

---

### search inside json based on a array of values. search()

```js
function search(arr, s) {
  var matches = [],
    i,
    key;

  for (i = arr.length; i--; )
    for (key in arr[i])
      if (arr[i].hasOwnProperty(key) && arr[i][key].indexOf(s) > -1)
        matches.push(arr[i]); // <-- This can be changed to anything

  return matches;
}

// dummy data
const items = [
  {
    foo: "bar",
    bar: "sit",
  },
  {
    foo: "lorem",
    bar: "ipsum",
  },
  {
    foo: "dolor",
    bar: "amet",
  },
];

var result = search(items, "lo"); // search "items" for a query value
console.log(result); // print the result
```

---

### String as the Search Expression

```js
var totn_string = "TechOnTheNet";

console.log(totn_string.search("T")); // 0
console.log(totn_string.search("t")); // 11
```

---

### Regular Expression as the Search Expression

```js
var totn_string = "TechOnTheNet";

console.log(totn_string.search(/[A-Z]/)); // 0
```

---

### find value inside array of objects json

```js
const data = [
  {
    name: "Afghanistan",
    code: "AF",
  },
  {
    name: "Åland Islands",
    code: "AX",
  },
  {
    name: "Albania",
    code: "AL",
  },
  {
    name: "Algeria",
    code: "DZ",
  },
];

function getCountryByCode(code) {
  return data.filter(function (data) {
    return data.code == code;
  });
}

console.log(getCountryByCode("DZ")); // 0: {code: "DZ", name: "Algeria" }
```

---

### Different ways to Loop through an array in JavaScript

```js
// ES4 Sequential for loop
var array = ["a", "b"];
var arrayLength = array.length;
for (var i = 0; i < arrayLength; i++) {
  console.log(array[i]);
  //Do something
}
```

```js
// ES5 Array.prototype.forEach
const data = ["a", "b", "c"];
data.forEach(function (item, index) {
  console.log(item, index); // a 0, b 1, c 2
});
```

```js
// ES6 for-of statement
let data = ["a", "b", "c"];
for (const a of data) {
  console.log(a); //
}
```

```js
// HoF reduce()
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((total, n) => total + n, 0);

console.log(sum); // 15
```

---

### Filter Array of object based on a value

```js
const people = [
  { name: "TK", age: 26 },
  { name: "Kaio", age: 10 },
  { name: "Kazumi", age: 30 },
];

// A better way to loop through: array of objects more HoF way
people.filter((a) => a.age > 21);
```

---

### Sum or add all Total values in an Array of object

1. OPTION 1

```js
const obj = {
  id: "1",
  key: "2",
};
const total = Object.keys(obj) // Get keys
  .map((key) => +obj[key]) // Get values as numbers
  .reduce((a, b) => a + b); // sum up

console.log(total); // 3
```

2. OPTION 2

```js
const foo = [
  { currency: "GBP", value: 123 },
  { currency: "GBP", value: 123 },
];
foo.map((x) => x.value).reduce((acc, next) => acc + next, 0); // 246
```

---


### Remove empty or blank spaces trimming the Array

```js
import { of, from } from "rxjs";
import { map, filter, tap } from "rxjs/operators";

const test1test1$ = from([" test ", " test ", " mas tests "])
  .pipe(map((x) => x.trim()))
  .subscribe((val) => console.log(val));
```

** Link:
https://stackblitz.com/edit/typescript-x7wjsm

---

### Filtering Array to take on just the strings

```js
arr = [5, "the fith element", 10, " element", true].filter(
  (x) => typeof x === "string"
); // ["the fith element", " element"]
```

---

### Modifying an Array of Objects

```js
var kvArray = [
  { key: 1, value: 10 },
  { key: 2, value: 20 },
  { key: 3, value: 30 },
];

reformattedArray = kvArray.map(function (obj) {
  var rObj = {}; // custom changes
  console.log(obj.key + " - " + obj.value); // choose your poison!
  rObj[obj.key] = obj.value;
  return rObj;
}); // 1 - 10, 2 - 20, 3 - 30
```

---

### Initialize / Creating a new Array of Objects based on old one values

```js
const arr = [
  {
    row1_name: "baz",
    row0_name: "foo",
    row1_value: 6,
    row0_value: 5,
    total: 2,
  },
].map((obj) => {
  let rObj1 = {};
  rObj1.name = obj.row1_name;
  rObj1.value = obj.row1_value;
  console.log(obj.row0_name);
  rObj2.name = obj.row0_name;
  rObj2.value = obj.row0_value;

  return { row: [rObj1, rObj2], total: 2 };
});

JSON.stringify(arr); // '[{"row":[{"name":"baz","value":6},{"name":"foo","value":5}],"total":2}]'
```

---


### groupBy and choose what to return usign Lodash

```js
var characters = [
  { name: "Juan", age: 30, pet: "dog" },
  { name: "Pepe", age: 31, pet: "dog" },
  { name: "Leo", age: 32, pet: "druf" },
  { name: "Carley", age: 12, pet: "goldfish" },
];
var result = _.chain(characters)
  .groupBy("name")
  .map((v, i) => {
    return {
      name: i,
      age: _.get(_.find(v, "age"), "age"),
      pet: _.map(v, "pet"),
    };
  });

console.log(JSON.stringify(result, null, " "));
```

```js
// count true and false Object literal
addressFields = [
  { name: "buildingNumberName", value: true },
  { name: "street", value: true },
  { name: "town", value: true },
  { name: "borough", value: true },
  { name: "county", value: true },
  { name: "postcode", value: false },
];
var count = 1,
  countFalse = 0;
for (var k in statusFormFields) {
  // if the object has this property and it isn't a property
  // further up the prototype chain
  if (statusFormFields[k].value === true) {
    console.log(statusFormFields[k].value, count++);
  } else {
    console.log(statusFormFields[k].value, (countFalse = countFalse + 1));
  }
}
```

---

### filter Object Literal based on another Object (using lodash)

```js
var users = [
  { user: "Leo", age: 21, active: true },
  { user: "Pepe", age: 22, active: false },
];

console.log(_.pluck(_.filter(users, { age: 21, active: true }), "user"));
```

---

### filter values based on portable logic

```js
// showMeTheMoreThan
function showMeTheMoreThan(value) {
  return value >= 10;
}
[12, 5, 8, 130, 44].filter(isBigEnough); // [12, 130, 44]
```

---


## simply apply a logic to every elemnt on array

```js
const myArr = [5, 10, 4, 50, 3];

multiplesOfFive = myArr.filter((x) => {
  return x % 5 === 0;
}); // [ 5, 10, 50 ]
```

---

## arr.map(callback[, thisArg])

> Simply applies the callback function on each item in the new array.

```js
// EJ.1
arr = [1, 2, 3, 4, 5];
newArr = arr.map((x) => {
  return x * 2;
});
console.log(newArr); // [2, 4, 6, 8, 10]
console.log(arr); // [1, 2, 3, 4, 5]
```

```js
// EJ.2
var numbers = [1, 5, 10, 15];
var roots = numbers.map((x) => {
  return x * 2;
});
console.log(numbers); // [1, 5, 10, 15]
console.log(roots); // [2, 10, 20, 30]
```

```js
// EJ.3
var numbers = [1, 4, 9];
var roots = numbers.map(Math.sqrt);
console.log(numbers); // [1, 4, 9]
console.log(roots); // [1, 2, 3]
```

---

## Simply accumulate all the clues of the array into one.

```js
const maxCallback = (pre, cur) => Math.max(pre.x, cur.x);
const maxCallback2 = (max, cur) =>
  Math.max(max, cur)[({ x: 22 }, { x: 42 })].reduce(maxCallback); // 42

[{ x: 22 }].reduce(maxCallback); // { x: 22 }
[].reduce(maxCallback); // TypeError
```

---

### sum all values from array of numbers

```js
const numbers = [1, 2, 3, 4];

numbers.reduce((x, y) => {
  return x + y;
}, 0); // 10
```

---

### get max value from array of numbers

```js
const numbers = [1, 2, 3, 4];

numbers.reduce((a, b) => {
  return Math.max(a, b);
}, 0); // 4
```

---

### return multiple by 4 of array

```js
const numbers = [1, 2, 3, 4];
const plusone = numbers.map((n) => n + 1);
const evens = plusone.filter((n) => n % 2 === 0);

var byfour = evens.reduce((groups, n) => {
  let key = n % 4 == 0 ? "yes" : "no";
  (groups[key] = groups[key] || []).push(n);
  return groups;
}, {}); // { 'yes': [4,8], 'no': [2,6,10] }
```

---

### get the total ammount of this objects

```js
var foo = [
  { a: 100, b: "red" },
  { a: 200, b: "blue" },
  { a: 300, b: "black" },
  { a: 400, b: "pink" },
];

totalAmount = foo.reduce((sum, x) => sum + x.a, 0); // 1000
```

---

#### calculate the sum of squares of all even numbers

```js
let numbers = [1, 2, 3, 4, 5];
let sumOfEvenSquares = _.chain(numbers)
  .filter((n) => n % 2 === 0)
  .map((n) => n * n)
  .sum()
  .value();

console.log(sumOfEvenSquares); //
```

---

#### Display a deep object from an Object Literal

```js
const a = {
  b: [
    {
      c: { name: "Leo" },
    },
  ],
};
a && a.b && a.b[0] && a.b[0].c && a.b[0].c.name; // 'Leo'
```

---

### debounce. Utility

Creates a debounced function that delays invoking the provided function until at least ms milliseconds have elapsed since the last time it was invoked.

```js
const debounce = (fn: Function, ms = 300) => {
  let timeoutId: ReturnType<typeof setTimeout>;
  return function (this: any, ...args: any[]) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn.apply(this, args), ms);
  };
};

window.addEventListener(
  "resize",
  debounce(() => {
    console.log(window.innerWidth);
    console.log(window.innerHeight);
  }, 250)
); // Will log the window dimensions at most every 250ms

let counter = 0;
const updateState = () => {
  counter++;
};
const debouncedUpdate = debounce(updateState);

debouncedUpdate(); // counter == 1
debouncedUpdate(); // counter == 1
await delay(300); // counter == 1
assertEquals(counter, 1);
debouncedUpdate(); // counter == 2
await delay(300); // counter == 2
assertEquals(counter, 2);
```

---

### Pick the key-value pairs corresponding to the given keys from an object. Utility

```js
const pick = (obj, arr) =>
  arr.reduce((acc, curr) => (curr in obj && (acc[curr] = obj[curr]), acc), {});

pick({ a: 1, b: "2", c: 3 }, ["a", "c"]); // { 'a': 1, 'c': 3 }
```

---

### memorize. Utility

Returns the memoized (cached) function.

> Create an empty cache by instantiating a new Map object. Return a function which takes a single argument to be supplied to the memoized function by first checking if the function's output for that specific input value is already cached, or store and return it if not. The function keyword must be used in order to allow the memoized function to have its this context changed if necessary. Allow access to the cache by setting it as a property on the returned function.

```js
const memoize = <T = any>(fn: Func<T>) => {
  const cache = new Map();
  const cached = function (this: any, val: T) {
    return cache.has(val)
      ? cache.get(val)
      : cache.set(val, fn.call(this, val)) && cache.get(val);
  };
  cached.cache = cache;
  return cached;
};

// See the `factorial` snippet.
const factorialCache = memoize(factorial);
factorialCache(6); // 720, little bit slow
factorialCache(6); // 720, slightly faster

// To get all cache
console.log(factorialCache.cache);
```

---

### count of elements in each group. Utility.

Groups the elements of an array based on the given function and returns the count of elements in each group.

```js
export const countBy = <T = any>(arr: T[], fn: Func<T> | string) => {
  const mapper = typeof fn === "function" ? fn : (val: any) => val[fn];
  return arr.reduce((acc, val) => {
    const value = mapper(val);
    acc[value] = (acc[value] || 0) + 1;
    return acc;
  }, {} as any);
};

countBy([6.1, 4.2, 6.3], Math.floor); // {4: 1, 6: 2}
countBy(["one", "two", "three"], "length"); // {3: 2, 5: 1}

countBy([{ name: "Deepak" }, { name: "Deepak2" }, { name: "Deepak" }], "name"); // { Deepak: 2, Deepak2: 1 }
countBy(
  [{ name: "Deepak" }, { name: "Deepak2" }, { name: "Deepak" }],
  (user: any) => user.name
); // { Deepak: 2, Deepak2: 1 }
```

---

### check if some of the elements of the array comply the requirement. `.some()`

```js
// ej 1)
[1,2,3].some( x => { return x > 5; }) // false
[1,2,3].some( x => { return x > 2; }) // true
[].some(x => { return true; }); // false
```

---

### check if string s1 contains / includes s2

Returns true if given string s1 contains s2. Compare is case insensitive.

```js
const contains = (s1: string, s2: string = "") =>
  s1.toLowerCase().indexOf(s2.toLowerCase()) !== -1;

contains("Text1", "Ext"); // true
contains("Text1", "et"); // false
```

---

### Get elements that are contain on both arrays. Contains.

> Use Array.prototype.filter() to remove values that are not part of values, determined using Array.prototype.includes()

```js
const similarity = (arr, values) => arr.filter((v) => values.includes(v));

similarity([1, 2, 3], [1, 2, 4]); // [1, 2]
similarity(
  [1, 2, 3, 4, null, NaN, undefined, ""],
  [1, 2, 3, null, undefined, ""]
); // [1, 2, 3, null, undefined, ""]
```

---

### check if array of strings contains / includes others elements from string

```js
// ej2
const str1 = "hi, how do you do?";
const str2 = "regular string";
const arr = ["hello", "hi", "howdy", "Leo"];

// run the tests agains every element in the array
arr.some((x) => str1.includes(x)); // true
arr.some((x) => str2.includes(x)); // false
```

---

### `.every()`

## If all values in array 'pass' conditional = true

```js
let arrayX = [1, 30, 39, 29, 10, 13];
function foo(x) {
  return typeof x === "number";
}

console.log(arrayX.every(foo)); // true
```

---

## validate all values from arrray even

```js
import { every } from "rxjs/operators";
import { of } from "rxjs";

//emit 5 values
const source = from([2, 4]);
const example = source.pipe(
  //is every value even?
  every((val) => val % 2 === 0)
);
const subscribe = example.subscribe((val) => console.log(val)); // true
```

---

## validate all values inside array are true. MB

```js
import { every } from "rxjs/operators";
import { of, from } from "rxjs";

//emit 5 values
const val1 = true;
const val2 = true;
const val3 = [val1, val2];

const source = from(val3);
const example = source.pipe(
  //is every value true
  every((val) => val === true)
);
//output: false
const subscribe = example.subscribe((val) => console.log(val));
```

---

## get specific entries inside an object

```js
const object1 = { foo: "bar", baz: 42 };
console.log(Object.entries(object1)[1]); // ["baz", 42]

const object2 = { 0: "a", 1: "b", 2: "c" };
console.log(Object.entries(object2)[2]); // ["2", "c"]
```

---

## Removing properties from an object

```js
const arr = [
  { name: "colin", car: "suzuki", age: 17 },
  { name: "leo", car: "audi", age: 40 }
];

const filteredArr = arr.filter(obj => obj.name !== "leo");

console.log(filteredArr); // [{ name: "colin", car: "suzuki", age: 17 }]
```

---

## Remove shortes words from string

```js
// better: using array.filter()
function dropShortWords(words) {
  const longWords = words.split(" ").filter((word) => {
    return word.length > 4;
  });
  return longWords.join(" ");
}

dropShortWords("The quick brown fox jumped over the lazy dog"); // "quick brown jumped"
```

---

### get array order / sorted by entries

```js
const result = Object.entries(object2).sort((a, b) => a - b);

console.log(Object.entries(result)[1]); // [["0", "a"], ["1", "b"], ["2", "c"]]
```

---

### iterate through key-value

```js
const obj = { a: 5, b: 7, c: 9 };

for (const [key, value] of Object.entries(obj)) {
  console.log(`${key} ${value}`); // "a 5", "b 7", "c 9"
}
```

---

### Display just values from an entries not keys

```js
const person = {
  name: "Leo",
  age: 30,
  occupation: "Engineer"
};

const valuesOnly = Object.entries(person).map(entry => entry[1]);

console.log(valuesOnly); // ["Leo", 30, "Engineer"]
```

---

### Display keys from the entries not values

```js
addressFields = [
  { name: "buildingNumberName", value: true },
  { name: "street", value: true },
  { name: "town", value: true },
  { name: "borough", value: true },
  { name: "county", value: true },
  { name: "postcode", value: true },
];

Object.keys(addressFields).length; // 6
```

---

### iterate across array of objects

```js
// iterate or search throgth object using for..in
var prop,
  obj = { name: "Joe", job: "Coder", age: 25 };
for (var prop in obj) {
  console.log(prop); // name, job, age
}
```

```js
// iterate or search across an object - using hasOwnProperty
var prop,
  obj = { name: "Joe", job: "Coder", age: 25 };
for (var prop in obj) {
  if (obj.hasOwnProperty(prop)) {
    console.log(prop + ": " + obj[prop]); //  name: Joe, job: Coder, age: 25
  }
}
```

```js
// iterate or search across an object - using typeof
for (var prop in obj) {
  if (typeof obj[prop] !== "function") {
    console.log(prop + ": " + obj[prop]);
  }
}
```

```js
// search across an object - using hasOwnProperty
var newBabeBorn,
  obj = {
    Name: "Tom Lanese",
    Cry: "All the time",
    Sleeping: "1.5hs",
    Feeding: "45m",
    Feeling: "Very Happy",
  };

function myLifeTheseDays() {
  for (var newBabeBorn in obj) {
    if (obj.hasOwnProperty(newBabeBorn) && obj[newBabeBorn] === "Tom Lanese") {
      console.log(newBabeBorn + ": " + obj[newBabeBorn]);
    }
  }
}

myLifeTheseDays(); // Name: Tom Lanese
```

---

#### Sum all objects but except 1

```js
let data = [{
    country: "China",
    pop: 1,
  },{
    country: "India",
    pop: 2,
  },{
    country: "USA",
    pop: 2,
  },{
    country: "Indonesia",
    pop: 2,
  },
];

// accumulate all but China
data.reduce((acc, val) => {
  return val.country === "China" ? acc : acc + val.pop;
}, 0); // 6
```

---

### remove duplicates / duplications in array

```js
const arr = [7, 3, 1, 3, 3, 7];

let uniqueArr = [...new Set(arr)]; // [7, 3, 1]
```

---

### .length of the <b>longest word in a string</b>

```js
function findLongestWord(str) {
  var longestWord = str.split(" ").sort((a, b) => b.length - a.length);
  console.log(longestWord[0]); // jumping
  return longestWord[0].length; // 7
}

findLongestWord("The red fox was jumping over the lazy dog"); // 7
```

---

### Iterate args and reduce in a unique return entity like your sum func

```js
const sum = (...args) => args.reduce((prev, curr) => prev + curr);

sum(1, 2, 3); // 6
```

---

### Calculate a Number's Factorial

```js
const factorialNumber = (number) =>
  number < 0
    ? (() => {
        throw new TypeError("No negative numbers please");
      })()
    : number <= 1
    ? 1
    : number * factorialNumber(number - 1);

factorialNumber(4); // 24
```

---

### Check if a Number Is a Power of Two

```js
const isNumberPowerOfTwo = number =< !!number && (number & (number - 1)) === 0;

isNumberPowerOfTwo(100); // false
isNumberPowerOfTwo(128); // true
```

---

### Max Element From an Array

```js
const maxElementsfromArray = (array, number = 1) =>
  [...array].sort((x, y) => y - x).slice(0, number);

maxElementsfromArray([1, 2, 3, 4, 5]); // 5
```

---

### Check if All Elements in an Array Are Equal

```js
const elementsAreEqual = (array) => array.every((el) => el === array[0]);

elementsAreEqual([2, 2, 2, 2]); // true
```

---

### Checks if all elements in an array pass a test (provided as a function)= not pure

```js
let contest = [
  { team: "A", phase: 1, points: 8 },
  { team: "A", phase: 1, points: 8 },
];

result = contest.every((team) => team.points >= 7); // true
```

---

### Get sumatory of values inside array of object

```js
let arr = [{
    id: 1,
    name: "Leo",
    years: 45,
  },{
    id: 2,
    name: "Tom",
    years: 5,
  },{
    id: 3,
    name: "Sam",
    years: 3,
  },{
    id: 4,
    name: "Carley",
    years: 40,
  },
];
arr.reduce((accumulator, currentValue, currentIndex, array) => {
  return accumulator + currentValue.years;
}, 0); // 93
```

---

#### get the first match array element

If no result found `Array.find()` returns undefined. You can use `||` to set a default value:

```js
const people = [
  { id: 1, name: "Ted" },
  { id: 2, name: "Marshall" },
  { id: 3, name: "Barney" },
];

const getNameByID = (id) =>
  (people.find((o) => o.id === id) || { name: null }).name;

console.log(getNameByID(1)); // Ted
console.log(getNameByID(50)); // null
```

---

## Display all the array (like loop)

```js
comst numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const plusone = numbers.map((n) => n); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

---


### Get the values from Object

```js
Object.values({ one: 1, two: 2 }); // [1, 2]
```

---

### Get the Keys from Object

```js
Object.keys({ one: 1, two: 2 }); // ["one", "two"]
```

---

### Adding a function to an Object:

```js
function buildMetadata(object) {
  let id = parseInt(object.id);
  let last = object.last || object.id;
  let hashCode = 1;
  return {
    id,
    last,
    hashCode,
    isSecureHash: function () {
      return hashCode >= 32;
    },
  };
}
buildMetadata({ id: 1, last: 2, 3: 3 }); // Object {id: 1, last: 2, hashCode: 1}
```

---

### Take the odd and even number from an array

```js
const arr = [1, 2, 3, 4, 5];

arr.map((x) => {
  console.log(x % 2);
  x % 2 === 0 ? console.log("odd") : console.log("even");
});
```

---

### numbers from array (interview question)

```js
const arr = [1, 4, undefined, null, 9, NaN, 10, ""];

console.log(arr.filter(Number)); // 1, 4, 9, 10
```

---

### Remove empty or blank spaces trimming the Array

```js
["     test   ", "   test    ", "    mas tests   "].map((x) => x.trim()); // ["test", "test", "mas tests"]
```

---

## Changing an array of Object using `generators`

> Generators are functions that can be paused and resumed, allowing for more flexible control flow

```js
const obj =  {one: "leo", two: "something"};

function* entries(obj) {
  for (const key of Object.keys(obj)) {
    yield [key, obj[key]];
  }
}

for (let [key, value] of entries(obj)) {
  console.log(key, value)
  if (key ===  'one'){
     value = 'LEO';
  }
  console.info(key, value);
}; // one leo
      one LEO
      two something
      two something
```

---

#### Find an object in an array by one of its properties

```js
var inventory = [
  { name: "ravi", quantity: 2 },
  { name: "toby", quantity: 0 },
  { name: "velu", quantity: 5 },
].find((x) => x.name == "ravi");

console.warn(inventory); // Object {name: "ravi", quantity: 2}
```

---

#### Find INDEX of an object in an array by one of its properties

```js
inventory = [
  { name: "apples", quantity: 2 },
  { name: "bananas", quantity: 0 },
  { name: "cherries", quantity: 5 },
].findIndex((x) => x.quantity >= 1);
```

---

#### display all keys and values

```js
addressFields = [
  { name: "buildingNumberName", value: true },
  { name: "street", value: true },
  { name: "town", value: true },
  { name: "borough", value: true },
  { name: "county", value: true },
  { name: "postcode", value: true },
];
var count = 1;
for (var k in statusFormFields) {
  // if the object has this property and it isn't a property
  // further up the prototype chain
  console.log(statusFormFields[k].name, statusFormFields[k].value);
  if (statusFormFields.hasOwnProperty(k)) {
    count++;
  } else {
  }
}
```

---

#### count true and false Object literal

```js
addressFields = [
  { name: "buildingNumberName", value: true },
  { name: "street", value: true },
  { name: "town", value: true },
  { name: "borough", value: true },
  { name: "county", value: true },
  { name: "postcode", value: false },
];
var count = 1,
  countFalse = 0;
for (var k in statusFormFields) {
  // if the object has this property and it isn't a property
  // further up the prototype chain
  if (statusFormFields[k].value === true) {
    console.log(statusFormFields[k].value, count++);
  } else {
    console.log(statusFormFields[k].value, (countFalse = countFalse + 1));
  }
}
```

---

#### show values that are bigger than in Array

```js
function showMeTheMoreThan(value) {
  return value >= 10;
}

[12, 5, 8, 130, 44].filter(isBigEnough); // [12, 130, 44]
```

---


#### filtering Array to take on by the strings

```js
arr = [5, "the fith element", 10, " element", true].filter(
  (x) => typeof x === "string"
); //  ["the fith element", " element"]
```

---


### return the % 5 of every value on the array

```js
const logic = x => x % 5 === 0;
const myArr = [5, 10, 4, 50, 3];

multiplesOfFive = myArr.filter(logic); // [ 5, 10, 50 ]
```

---

### applies the callback function on each item in the new array.

// EJ1
```js
arr = [1, 2, 3, 4, 5];
newArr = arr.map(function (x) {
  return x * 2;
});

console.log(newArr); // [2, 4, 6, 8, 10]
console.log(arr); // [1, 2, 3, 4, 5]
```

// EJ2

```js
var numbers = [1, 5, 10, 15];
var roots = numbers.map(function (x) {
  return x * 2;
});

console.log(numbers); // [1, 5, 10, 15]
console.log(roots); // [2, 10, 20, 30]
```

// EJ3

```js
var numbers = [1, 4, 9];
var roots = numbers.map(Math.sqrt);

console.log(numbers); // [1, 4, 9]
console.log(roots); // [1, 2, 3]
```

---

## A method creates a new array with the results, and keep the old one

```js
// eg1
var numbers = [1, 5, 10, 15];
var roots = numbers.map((x) => x * 2); // [2, 10, 20, 30]
```

```js
// eg2
const myArr = ["some text", "more text", "final text"];
const mappedArr = myArr.map( (str) => {
  return str.split(" ");
});

console.log(mappedArr);
// [[ 'some', 'text' ], [ 'more', 'text' ], [ 'final', 'text' ]]
```

---

## Simply accumulate all the clues of the array into one

> arr.reduce(callback [, initalValue]);


```js
// Ej1
var maxCallback = (pre, cur) => Math.max(pre.x, cur.x);
var maxCallback2 = (max, cur) => Math.max(max, cur);

[{ x: 22 }, { x: 42 }].reduce(maxCallback) // 42
[{ x: 22 }].reduce(maxCallback) // { x: 22 }
[].reduce(maxCallback) // TypeError
```

```js
// EJ2
var numbers = [1, 2, 3, 4];
numbers.reduce(function (x, y) {
  return x + y;
}, 0); // 10
```


```js
// EJ3 (get max)
var numbers = [1, 2, 3, 4];
numbers.reduce(function (a, b) {
  return Math.max(a, b);
}, 0); // 4
```

```js
// EJ4
var byfour = evens.reduce((groups, n) => {
  let key = n % 4 == 0 ? "yes" : "no";
  (groups[key] = groups[key] || []).push(n);
  return groups;
}, {}); // byfour: { 'yes': [4,8], 'no': [2,6,10] }
```

---

## Pick Intersection between arrays

```js
const logic = (x) => arr2.includes(x);
const arr1 = [1, 2, 3];
const arr2 = [2, 3];

arr1.filter(logic); // [2, 3]
```

```js
// or instead
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [6, 7, 8, 9, 10];
const arrx = [arr1, arr2];

arrx.flat(); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

---

## Get params from url path

```js
const getPathParams = (path, pathMap, serializer) => {
  path = path.split("/");
  pathMap = pathMap.split("/");
  return pathMap.reduce((acc, crr, i) => {
    if (crr[0] === ":") {
      const param = crr.substr(1);
      acc[param] =
        serializer && serializer[param] ? serializer[param](path[i]) : path[i];
    }
    return acc;
  }, {});
};

getPathParams("/app/products/123", "/app/:page/:id");
// { page: 'products', id: '123' }

getPathParams("/items/2/id/8583212", "/items/:category/id/:id", {
  category: (v) => ["Car", "Mobile", "Home"][v],
  id: (v) => +v,
}); // { category: 'Home', id: 8583212 }
```

---

## Generate url path with query string

```js
const generatePathQuery = (path, obj) =>
  path +
  Object.entries(obj)
    .reduce((total, [k, v]) => (total += `${k}=${encodeURIComponent(v)}&`), "?")
    .slice(0, -1);

generatePathQuery("/user", { name: "Leo", age: 30 }); // '/user?name=Leo&age=30'
```

---

## Get params from query string

```js
const getQueryParams = (url) =>
  url.match(/([^?=&]+)(=([^&]*))/g).reduce((total, crr) => {
    const [key, value] = crr.split("=");
    total[key] = value;
    return total;
  }, {});

getQueryParams("/user?name=Orkhan&age=30"); // { name: 'Orkhan', age: '30' }
```

---

## Detect Odd or Even

```js
const value = 232;

value & 1 ? console.log("odd") : console.log("even"); // even
```

---

## Generate a list with random numbers

```js
Array.from({ length: 10 }, Math.random);
// [0.3886203851174783, 0.01916402372421433, 0.07179086933979262, 0.9828766496408043, 0.2777564147951399, 0.8566450363933746, 0.5938766022993569, 0.6188080148700192, 0.34474210354432056, 0.2953952018657524]
```

---

### Is Object. Utility

```js
const isObject = (obj) => obj === Object(obj);

isObject([1, 2, 3, 4]); // true
isObject([]); // true
isObject(["Hello!"]); // true
isObject({ a: 1 }); // true
isObject({}); // true
isObject(true); // false
```

---

### Returns true if the specified value is null or undefined, false otherwise. Utility

```js
const isNil = (val) => val !== undefined && val !== null && Number.isInteger(var);

isDefNum(null); // true
isDefNum(undefined); // true
isDefNum(""); // false
```

---

### Returns true if the specified value is null, undefined or return false otherwise. Utility


```js
const isNil = (val) => val === undefined || val === null;

isNil(null); // true
isNil(undefined); // true
isNil(""); // false
```

---

## check if empty. utility

Returns true if the a value is an empty object, collection, has no enumerable properties or is any type that is not considered a collection.

```js
const isEmpty = (val: any) => val == null || !(Object.keys(val) || val).length;

isEmpty(); // true
isEmpty(null); // true
isEmpty(undefined); // true
isEmpty([]); // true
isEmpty({}); // true
isEmpty(''); // true
isEmpty([1, 2]); // false
isEmpty({ a: 1, b: 2 }); // false
isEmpty("text"); // false
isEmpty(123); // true - type is not considered a collection
isEmpty(true); // true - type is not considered a collection
```

---

## Returns the last element of array. Utility. MB

```js
const last = (arr: any[] = []) => arr[arr.length - 1];

last([1, 2, 3]); // 3
last([]); // undefined
last([null]); // null
last(undefined); // undefined
```

---

## Make a function is called only once. Utility. MB

```js
const once = (fn) => {
  let called = false;
  return function (...args) {
    if (called) return;
    called = true;
    return fn.apply(this, args);
  };
};

const startApp = function (event) {
  console.log(this, event); // document.body, MouseEvent
};
document.body.addEventListener("click", once(startApp)); // only runs `startApp` once upon click
```

---

## Gets size: array, object, blob or string. Utility

```js
const sizeOf = (val: any) =>
  Array.isArray(val)
    ? val.length
    : val && typeof val === "object"
    ? val.size || val.length || Object.keys(val).length
    : typeof val === "string"
    ? new Blob([val]).size
    : 0;

size([1, 2, 3, 4, 5]); // 5
size("size"); // 4
size({ one: 1, two: 2, three: 3 }); // 3
```

---

## Defer invoking a function until the current call stack has cleared. utility

```js
const defer = (fn, ...args) => setTimeout(fn, 1, ...args);

// Example A:
defer(console.log, "a"), console.log("b"); // logs 'b' then 'a'

// Example B:
document.querySelector("#someElement").innerHTML = "Hello";
longRunningFunction(); // Browser will not update the HTML until this has finished
defer(longRunningFunction); // Browser will update the HTML then run the function
```

---

## Measures the time taken by a function to execute. Utility


```js
const timeTaken = (callback: Function) => {
  const id = `timeTaken_${Date.now()}`;
  console.time(id);
  const r = callback();
  console.timeEnd(id);
  return r;
};

timeTaken(() => Math.pow(2, 10)); // 1024, (logged): timeTaken: 0.02099609375ms
```

---

## find max number in Array

```js
function findMax(arr) {
  return Math.max(...arr);
}
findMax([10,-4,6,12,3,-1,0]) //
findMax([0,100,500,-105,-102,30]) // 
```

---

## Check if an Element is Focused

```js
const hasFocus = (element) => element === document.activeElement;
```

---

## console.trace()

```js
function outerFunction() {
  function innerFunction() {
    console.trace();
  }
  innerFunction();
}
outerFunction();
```

---

## use `[].includes` instead of `||`

```js
// ❌ instead of 💩
const checkNames = (name) => {
  if (name === 'medium' || name === 'fatfish') {
    return true
  }
  return false
}

checkNames('medium') // true
checkNames('fatfish') // true
checkNames('JavaScript') // false

// Better do ✅
const checkNames = (name) => {
  const names = [ 'medium', 'fatfish', 'JavaScript' ]  // You just need to add a new name to the names array
  return names.includes(name)
}

checkNames('medium') // true
checkNames('fatfish') // true
checkNames('JavaScript') // false
```

---

## YAY ! playing with Array of Object. mb

## Remove Multiple Elements index from an Array in JavaScript

```js
const valuesArr = ["v1", "v2", "v3", "v4", "v5"];
const removeValFromIndex = [0, 2, 4];

const filterbyIndex = valuesArr.filter((value, index) => {
  return !removeValFromIndex.includes(index);
})

console.log(filterbyIndex); // ['v2', 'v4']
```

---

## filter Array of object based on 2 values

```js
const pets = [
  { type: "Dog", name: "Leo" },
  { type: "Cat", name: "Sam" },
  { type: "Dog", name: "Tom" },
];

pets.find(pet => 
          pet.type === "Dog" && 
          pet.name === "Tom"); // {type: 'Dog', name: 'Tom'}
```

---

## Filter Array Of Object when: key === 38

```js
[
  { name: "Zak", age: 25 },
  { name: "Adel", age: 38 },
  { name: "Yori", age: 28 },
].filter(x => 
         x.age === 38); // Object {name: "Abel", age: 38}
```

---

## Filter arra of objects when: name === "Adel"

```js
const aoo = [
  {
    name: "Leo",
    age: 25,
  },
  {
    name: "Tom",
    age: 38,
  },
  {
    name: "Sam",
    age: 28,
  },
].filter(arr => 
         arr.name === "Adel"); // [{age:38, name:"Adel"}]
```

---

## adding a field into and array of objects

```js
const test = [
  { key: 1, value: 10 },
  { key: 2, value: 20 },
  { key: 3, value: 30 },
];

const reformattedArray = test.map(obj => ({
  [obj.key]: obj.value,
  test: "Leo"
}));

console.log(reformattedArray);
// [{1: 10, test: "Leo"},
//  {2: 20, test: "Leo"},
//  {3: 30, test: "Leo"}]
```

---

## Filter the biggest value from all array of objects

```js
let arr = [
  {
    id: 1,
    name: "Leo",
    years: 45,
  },
  {
    id: 2,
    name: "Tom",
    years: 5,
  },
  {
    id: 3,
    name: "Sam",
    years: 3,
  },
  {
    id: 4,
    name: "Carley",
    years: 40,
  },
];
arr.reduce((accumulator, currentValue, currentIndex, array) => {
  return accumulator.years > currentValue.years ? accumulator : currentValue;
}, 0); // {id: 1, name: "Leo", years: 45}
```

---

## filter and Array of Object based on another object value

```js
const arr = [
  { id0: "Accept" },
  { id1: -1 },
  { id2: 0 },
  { id3: 3 },
  { id4: 12.2 },
  { id5: null },
  { id6: "Leo" },
  { id7: "undefined" },
];

const lookingKey = 'id6';

function filterByID(obj) {
  console.warn('Evaluating:', obj)
  return (lookingKey in obj) ? true : false; 
}
const arrByID = arr.filter(filterByID); 
console.log(arrByID); // {id6 :"Leo"}
```

---

## Count number objects on Array of Objects

```js
addressFields = [
  { name: "building", value: true },
  { name: "street", value: true },
  { name: "town", value: true },
  { name: "borough", value: true },
  { name: "county", value: true },
  { name: "postcode", value: true },
];

Object.keys(addressFields).length; // 6
```

---

## Filtering the array of objects on the basis of specific key value.

```js
[
  { name: "Zak", age: 25 },
  { name: "Adel", age: 38 },
  { name: "Yori", age: 28 },
].filter(x => 
         x.age === 38); // Object {name: "Abel", age: 38}
```

---

## Iterate Array of object

```js
// eg1
const container = [
  { background: "#CFEBB3", color: "#000", cursor: "blackCursor" },
  { background: "#C0E1A0", color: "#111" },
  { background: "#95CD61" },
  { background: "#85B100" },
  { background: "#FED003", color: "#000" },
];
Object.keys(container).forEach((key, index) => {
  // key: the name of the object key
  // index: the ordinal position of the key within the object
  console.log(key, container[key], index);
});
```

```js
// wg2
const obj = { one: 1, two: 2 };

for (let [k, v] of Object.entries(obj)) {
  console.log(`${JSON.stringify(k)}: ${JSON.stringify(v)}`); // "one": 1, "two": 2
}
```

---

## Accumulate a number value from Array of Objects

```js
const items = [
  { id: 1, name: "Super Burger", price: 1 },
  { id: 2, name: "Jumbo Fries", price: 2 },
  { id: 3, name: "Big Slurp", price: 3 },
];

const AccumulatedPrice = items.reduce((prev, next) => prev + next.price, 0);

console.log(AccumulatedPrice); // Total: 6
```

---

## Changing an Array of Objects

```js
const kvArray = [
  { key: 1, value: 10 },
  { key: 2, value: 20 },
  { key: 3, value: 30 },
];

reformattedArray = kvArray.map(obj => {
  const rObj = {}; // custom changes
  console.log('original:', obj.key + " - " + obj.value); // choose your poison!
  rObj[obj.key] = obj.value + 1;
  return rObj;
}); //  1 - 11, 2 - 21, 3 - 31
```

---

## `get every property` check validation `by another property` from Array of Objects

```js
const sales = [
  { product: "iPhone", price: 999, sales: 45, id: 0 },
  { product: "S10", price: 999, sales: 45, id: 1 },
  { product: "Ipad", price: 66, sales: 45, id: 2 },
];
const priceMore100 = (x) => x.price >= 100;
const priceMore66 = (x) => x.price >= 66;

const result1 = sales.every(priceMore100); // false
const result2 = sales.every(priceMore66); // true
```

---

## FILTER by KEY. filter array of objects by key (key = name)

```js
[
  { name: "Leo", age: 45 },
  { name: "Tom", age: 7 },
  { name: "Sam", age: 6 },
].map(a => 
      a.name); // ["Leo", "Tom", "Sam"];
```

```js
/// SAME but using RxJS
import { of, from } from "rxjs";
import { map, filter, tap } from "rxjs/operators";

const stream$ = from([
  { name: "Zak", age: 25 },
  { name: "Adel", age: 38 },
  { name: "Yori", age: 28 },
])
  .pipe(map((a) => a.name))
  .subscribe((val) => console.log(val));
```

** Links:
https://stackblitz.com/edit/typescript-bmzygi

---

## Filter Array Of Object based on condition

```js
const filterLogic = x => 
                    x.price >= 500 && 
                    x.price <= 600;

const arr = [
  {
    name: "Tom",
    price: 500,
  },{
    name: "Sam",
    price: 600,
  },{
    name: "Leo",
    price: 1000,
  },
];

const immutableResult = arr.filter(filterLogic);
// [{name: "Tom", price: 500}, {name: "Sam", price: 600}]
```

---

## Filter Array of objects by KEY

```js
const logic = x => x.age === 38;
const foo = [
  {
    name: "Zak",
    age: 25,
  },{
    name: "Adel",
    age: 38,
  },{
    name: "Yori",
    age: 28,
  },
]

const result = foo.filter(logic); // {name: "Abel", age: 38}
```

---

## Find if Object exist inside Array of objects

```js
const ivma = [
  { name: "ravi", order: 1 },
  { name: "toby", order: 2 },
  { name: "velu", order: 3 },
].find(x => {
  x.name === 'ravi' 
  ? console.log(x.order) 
  : ""; // 1
});
```

```js
// same but using RXJS
import { of, from } from "rxjs";
import { map, filter, tap } from "rxjs/operators";

const rav = "ravi";
const inventory$ = from([
  { name: "ravi", quantity: 2 },
  { name: "toby", quantity: 0 },
  { name: "velu", quantity: 5 },
])
  .pipe(filter((x) => x.name === "ravi"))
  .subscribe((val) => console.log(val));
```

** Links:
https://stackblitz.com/edit/typescript-dr5s3r

---

## Search in array of object Array values

Filter object by array of object base on array

```js
// option 1
// array of object
const items = [
  {
    foo: "test",
    tasdd: "sit",
  },
  {
    foo: "lorem",
    test: "ipsum",
  },
  {
    foo: "dolor",
    bar: "amet",
  },
];

// array
const arr = ["amet", "ipsum"]; 

// reusable function
function searchObject(arr, s) {
  var matches = [], i,key;

  for (i = arr.length; i--; )
    for (key in arr[i])
      if (arr[i].hasOwnProperty(key) && arr[i][key].indexOf(s) > -1)
        matches.push(arr[i]); // <-- This can be changed to anything
  return matches;
}


for (const key in arr) {
  console.log(arr[key] + JSON.stringify(searchObject(items, arr[key])));
}
// amet[{"foo":"dolor","bar":"amet"}]
// ipsum[{"foo":"lorem","test":"ipsum"}]
```

```js
// option 2 (shorter)
// array of object
const items = [
  {
    foo: "test",
    tasdd: "sit",
  },
  {
    foo: "lorem",
    test: "ipsum",
  },
  {
    foo: "dolor",
    bar: "amet",
  },
];

// array
const arr = ["amet", "ipsum"]; 

function filtering(array, value, key) {
  return array.filter(
    key
      ? (items) => items[key] === value
      : (items) => Object.keys(items).some((k) => items[k] === value)
  );
}

for (const key in arr) {
  arr[key] + JSON.stringify(filtering(items, arr[key])); 
}
// 'ipsum[{"foo":"lorem","test":"ipsum"}]'
```

---

## Copy a new array

```js
const arr = [ 'fatfish', 'medium', [ 'JavaScript', 'NodeJs' ] ]
const copyArr = [ ...arr ]

// If we change the third element, the "arr" will also be change.
copyArr[ 2 ][ 0 ] = 'FrontEnd'
console.log(copyArr) // [ 'fatfish', 'medium', [ 'FrontEnd', 'NodeJs' ] ]

// The arr also changed
console.log(arr) // [ 'fatfish', 'medium', [ 'FrontEnd', 'NodeJs' ] ]
```

---

## Search in array of object an Array value

```js
var data = [
  { text: "John is better than me", string: "I'm ok" },
  { text: "last but not least", string: "for sure" },
];

var arr = ["than"]; // second array

arr.forEach((element) => {
  data.filter((item) => {
    return item.text.includes(element);
  });
}); // true, false
```

---

## Multiple string checks

```js
// Long-hand
const isVowel = (letter) => {
    if (
    letter === "a" ||
    letter === "e" ||
    letter === "i" ||
    letter === "o" ||
    letter === "u"
    ) {
        return true;
        }
        return false;
        };
        // Short-hand
        const isVowel = (letter) =>
        ["a", "e", "i", "o", "u"].includes(letter);
```


---

### Find and change array of objects

```js
const familyList = [{
    name: 'Lanese',
    members: {
      name: 'Leo'
    }
  },{
    name: 'Cavalieri',
    members: {
      name: 'Leonora'
    }
  }
];
```

```js
// ❌ instead of 💩
familyList.forEach(family => {
  if (family.name === 'Lanese') {
    family.name = '---Lanese---'
  }
})

// Better do ✅
const findLanese = familyList.find(
    family => family.name === 'Lanese'
  )
findLanese.name = '---Lanese---';  
```

---

## Count Properties of an Array of Objects

> Need to count the number of items in an array that match a particular property

```js
const countElementsByProp = (arr, prop) =>
  arr.reduce(
    (prev, curr) => ((prev[curr[prop]] = ++prev[curr[prop]] || 1), prev),
    {}
  );
// example
countElementsByProp(
  [
    { manufacturer: "audi", model: "q8", year: "2019" },
    { manufacturer: "audi", model: "rs7", year: "2020" },
    { manufacturer: "ford", model: "mustang", year: "2019" },
    { manufacturer: "ford", model: "explorer", year: "2020" },
    { manufacturer: "bmw", model: "x7", year: "2020" },
  ],
  "manufacturer"
); // { 'audi': 2, 'ford': 2, 'bmw': 1 }
```

---

## Filter an array of objects based on 2 fields

Having 1 array of object, pick intersection between them

```js
const data = [{
    CATEGORY: "C003",
    Subcategory: "SC003",
    Model: "MDL003",
    MAKE_NAME: "MAKE003",
    ModelType: "MT003",
    Tier: "T003",
  },{
    CATEGORY: "C004",
    Subcategory: "SC004",
    Model: "MDL004",
    MAKE_NAME: "MAKE004",
    ModelType: "MT004",
    Tier: "T004",
  },{
    CATEGORY: "C001",
    Subcategory: "SC001",
    Model: "MDL001",
    MAKE_NAME: "MAKE001",
    ModelType: "MT001",
    Tier: "T001",
  },{
    CATEGORY: "C002",
    Subcategory: "SC002",
    Model: "MDL002",
    MAKE_NAME: "MAKE002",
    ModelType: "MT002",
    Tier: "T002",
  },
];

const filters = {
  CATEGORY: ["C004", "C001"],
  Model: ["MDL002"],
};

// ignores case-sensitive
const getValue = (value) =>
  typeof value === "string" ? value.toUpperCase() : value;

function pickPlainArrayWithOR(array, filters) {
  const filterKeys = Object.keys(filters);
  return array.filter((item) => {
    // filters using the (OR) operator
    return filterKeys.some((key) => {
      // ignores an empty filter
      if (!filters[key].length) return true;
      return filters[key].find(
        (filter) => getValue(filter) === getValue(item[key])
      );
    });
  });
}

const filteredList = pickPlainArrayWithOR(data, filters);
console.log(filteredList);

/*
[{ 
  "CATEGORY": "C004", "Subcategory":"SC004", "Model":"MDL004", "MAKE_NAME":"MAKE004", "ModelType":"MT004", "Tier":"T004" },
  { "CATEGORY": "C001", "Subcategory":"SC001", "Model":"MDL001", "MAKE_NAME":"MAKE001", "ModelType":"MT001", "Tier":"T001" },
  { "CATEGORY": "C002", "Subcategory":"SC002", "Model":"MDL002", "MAKE_NAME":"MAKE002", "ModelType":"MT002", "Tier":"T002" }];
*/
```

---

## Intersection: Pick between. MB

Find all values that are present in between: array-array and array of objects as defined by a keying-function.

```js
const intersectionBy = (fn, listA, listB) => {
  const b = new Set(listB.map(fn));
  return listA.filter(val => b.has(fn(val)));
};

intersectionBy(v => v, [1, 2, 3], [2, 3, 4]); // [2, 3]
intersectionBy(v => v.a, [{ a: 1 }, { a: 2 }], [{ a: 2}, { a: 3 }, { a: 4 }]); // [{ a: 2 }];
```

---

### Difference/Complement between 2 array of objects. MB

```js
// eg1
const myArray = [
  { name: "Leo", place: "Rosario" },
  { name: "Tom", place: "London" },
  { name: "Sam", place: "London" },
  { name: "Carley", place: "London" },
];

const toRemove = [
  { name: "Leo", place: "Rosario" },
  { name: "Tom", place: "London" },
];

difference = myArray.filter(
  (ar) => !toRemove.find((rm) => rm.name === ar.name && ar.place === rm.place)
); 
// {name: "Sam", place: "London"}, 
// {name: "Carley", place: "London"}
```

```js
// eg2
function arrayDiffByKey(key, ...arrays) {
  return [].concat(
    ...arrays.map((arr, i) => {
      const others = arrays.slice(0);
      others.splice(i, 1);
      const unique = [...new Set([].concat(...others))];
      return arr.filter((x) => !unique.some((y) => x[key] === y[key]));
    })
  );
}

const a = [{ k: 1 }, { k: 2 }, { k: 3 }];
const b = [{ k: 1 }, { k: 4 }, { k: 5 }, { k: 6 }];
const c = [{ k: 3 }, { k: 5 }, { k: 7 }];
arrayDiffByKey("k", a, b, c); // (4) [{k:2}, {k:4}, {k:6}, {k:7}]
```

---

## Filter/filtering Array of Object practices: `find`, `some` and `every` instead `filter`

```js
const peoples = [
  { name: "Bruce Wayne", country: "USA", city: "Gotham" },
  { name: "Leo", country: "Argentina", city: "Rosario" },
];

// use "find" instead "filter()[0]"
const isBruceWayne = (person) => person.name === "Bruce Wayne";

peoples.filter(isBruceWayne)[0]; // BAD
peoples.find(isBruceWayne); // GOOD

// use "some" instead "filter()[0]"
const isFromTheUSA = (person) => person.country === "USA";

// has peoples from USA?
!!peoples.filter(isFromTheUSA)[0]; // BAD
peoples.some(isFromTheUSA); // GOOD

// use "every" some instead: "filter()[0]"
const isNotFromTheUSA = (person) => person.country !== "USA";

!peoples.filter(isNotFromTheUSA)[0]; // BAD
peoples.every(isFromTheUSA); // GOOD
```

---

## sort array of object descending

```js
const aoo = [
  { name: "Leo", rating: 1 },
  { name: "Carley", rating: 2 },
  { name: "Tom", rating: 3 },
  { name: "Sam", rating: 4 },
];
aoo.sort((a, b) => b.rating - a.rating);
// [
//  {name: 'Sam', rating: 4}, {name: 'Tom', rating: 3}
//  {name: 'Carley', rating: 2}, {name: 'Leo', rating: 1}
// ]
```

## select / take only first key from array of objects

```js
let flia = [
  { name: "Leo", age: "45" },
  { name: "Caley", age: "40" },
  { name: "Tom", age: "5" },
  { name: "Sam", age: "3" },
];

Array.from(flia, ({ name }) => name); // ["Leo", "Caley", "Tom", "Sam"]
Array.from(flia, ({ age }) => age); // ["45", 40", "5", "3"]
```

---

## Dynamically exclude/remove Properties of array of object

> `prop` can be excluded dynamically from the clone

```js
const user1 = {
  id: 100,
  name: "Howard Moon",
  password: "Password!",
};

const removeProperty =
  (prop) =>
  ({ [prop]: _, ...rest }) =>
    rest;
const user1 = {
  id: 100,
  name: "Howard Moon",
  password: "Password!",
};

const removePassword = removeProperty("password");
const removeId = removeProperty("id");

removePassword(user1); // { id: 100, name: 'Howard Moon' }
removeId(user1); // { name: 'Howard Moon', password: 'Password!' }
```

---

## Dynamically Renaming Properties of array of object

```js
const renamed = ({ ID, ...object }) => ({ id: ID, ...object });
const user = {
  ID: 500,
  name: "Bob Fossil",
};

renamed(user); //  { id: 5000, name: 'Bob Fossil' }
```

---

## `Remove object` from Array of Object (Non-Mutating)

```js
let arr = [
  { a: 1, b: 2 },
  { a: 3, b: 4 },
  { a: 5, b: 6 },
];

n = arr.filter((x) => x.a !== 1); // {'a':3,'b':4}, {'a':5,'b':6}
```

---

### `Remove element` from array of Objects with slice

```js
let arr = [
  { a: 1, b: 2 },
  { a: 3, b: 4 },
  { a: 5, b: 6 },
];
let index = 2;

function removeItemWithSlice(index) {
  return [...arr.slice(0, index), ...arr.slice(index + 1)];
}

removeItemWithSlice(index); // [{a: 1, b: 2}, {a: 3, b: 4}]
```

---

## Unique object of an Array of object. Remove duplicates/duplication arrays of aobject. utility. mb

```js
// Code
const uniqueBy = (fn: Predicate, arr: any[]) =>
  arr.reduce((acc, v) => {
    if (!acc.some((x: any) => fn(v, x))) acc.push(v);
    return acc;
  }, []);

uniqueBy(
(a: any, b: any) => a.id == b.id,
  [
    { id: 0, value: "a" },
    { id: 1, value: "b" },
    { id: 2, value: "c" },
    { id: 1, value: "d" },
    { id: 0, value: "e" },
  ],
);
//  [{ id: 0, value: 'a' },
//   { id: 1, value: 'b' },
//   { id: 2, value: 'c' }]
```

---

## Picker / Find and take from nested array of object. MB

find object inside Array of object and return it if is not undefined

```js
// nested object
const obj = {
  selector: { to: { val: "val to select" } },
  target: [1, 2, { a: "test" }],
};

const picker = (from, ...selectors) =>
  [...selectors].map((s) =>
    s
      .replace(/\[([^\[\]]*)\]/g, ".$1.")
      .split(".")
      .filter((t) => t !== "")
      .reduce((prev, cur) => prev && prev[cur], from)
  );

picker(obj, "selector.to.val", "target[0]", "target[2].a"); // ['val to select', 1, 'test']
```

---

## Picker / Selector from array of object. Improved version to use buyState. MB

```js
const picker = (from, ...selectors) =>
  [...selectors].map(s =>
    s
      .split(".")
      .filter((key) => key !== undefined)
      .reduce((prev, cur) => prev && prev[cur], from)
  );

picker(buyState, "target.optionInterstitialScreen");
// {components: Array(5), type: 2, screenName: 'Buy: Card Instant Buy'}
```

---

## Picker / selector from array of objects. Simplest version. MB

```js
const pick = (obj, arr) =>
  arr.reduce(
    (acc, record) => (record in obj && (acc[record] = obj[record]), acc),
    {}
  );

pick({ a: "1", b: "2", c: "3" }, ["a", "c"]); // { 'a': 1, 'c': 3 }
pick({ a: 1, b: "2", c: 3 }, ["x", "c"]); // { 'c': 3 }
pick(buyState.target, ["optionInterstitialScreen"]); // optionInterstitialScreen: {components: Array(5), type: 2, screenName: 'Buy: Card Instant Buy'}
```

---

## reduce / filter array of object

> Filter an array of objects based on a condition while also filtering out unspecified keys.

>  only the second object in data has an age greater than 24, and we're only including the id and name properties in the output.

```js
const reducedFilter = (data, keys, fn) =>
  data.filter(fn).map((el) =>
    keys.reduce((acc, key) => {
      acc[key] = el[key];
      return acc;
    }, {})
  );

const data = [
  {
    id: 1,
    name: "john",
    age: 24,
  },{
    id: 2,
    name: "mike",
    age: 50,
  },
];

reducedFilter(data, ["id", "name"], (item) => item.age > 24); // [{ id: 2, name: 'mike'}]
```

---

## Get max / maximun value number from Array of objects

```js
const characters = [
  { id: 1, first: "Tim", last: "Draper" },
  { id: 17, first: "Tim", last: "Boies" },
  { id: 199, first: "Tim", last: "Kemp" },
  { id: 75, first: "Tim", last: "Mosley" },
  { id: 444, first: "Tim", last: "Holmes" },
  { id: 95, first: "Donald", last: "Lucas" },
  { id: 186, first: "Larry", last: "Ellison" },
  { id: 364, first: "Channing", last: "Robertson" },
  { id: 285, first: "Charles", last: "Fleischmann" },
  { id: 33, first: "John", last: "Howard" },
];

characters.reduce(
  (max, character) => (character.id > max ? character.id : max),
  characters[0].id
); // 444
```

---

## sort ascending Array of Objets function

```js
let data = [
  { name: 'abc', value: 21 },
  { name: 'cde', value: 37 },
  { name: 'ee', value: 45 },
  { name: 'ff', value: -12 },
  { name: 'ab', value: 13 },
  { name: 'cs', value: 37 }
];

data.sort((a, b) => return a.value - b.value);
```

---

## The number of days between two dates

```js
const dayDiff = (date1, date2) => Math.ceil(Math.abs(date1.getTime() - date2.getTime()) / 86400000);

dayDiff(new Date("2021-10-21"), new Date("2022-02-12")); // 114
```

---

## Check that the current TAB is in the background

```js
const isTabActive = () => !document.hidden;isTabActive(); // true|false
```

---

## Reverse. Reverse Array of objects

> reverse can reverse Arrays, but not Array of objects: When you reverse an array of objects, it's the order of the objects in the array that gets reversed, not the properties within each object.


```js
const test = [{ x: 1 }, { x: 2 }, { x: 3 }];

test.reverse(); // [ { x: 3 }, { x: 2 }, { x: 1 }]
```

> While the output may appear the same for this particular case, the key difference lies in the state of the original array after executing the reverse() method.
> if you want to reverse an Array of Objects, the better way will be clone it and reverse cloned:

```js
const test2 = [{ x: 1 }, { x: 2 }, { x: 3 }];

console.log([...test2].reverse()); // [ { x: 3 }, { x: 2 }, { x: 1 }]
```

---

## Pick value in a nested JSON object, based on the given key

```js
const nestedObject = {
  level1: {
    level2: {
      level3: "some data"
    },
  },
};

const dig = (obj, target) =>
  target in obj
    ? obj[target]
    : Object.values(obj).reduce((acc, val) => {
        if (acc !== undefined) return acc;
        if (typeof val === "object") return dig(val, target);
      }, undefined);

dig(nestedObject, "level3"); // 'some data'
dig(nestedObject, "level4"); // undefined
```

---

## Remove object from array of object based on condition

```js
const arr = [
  { a: 1, b: 2 },
  { a: 3, b: 4 },
  { a: 5, b: 6 },
];

n = arr.filter(x => 
               x.a !== 1); 

// [{'a':3,'b':4}, 
//  {'a':5,'b':6}]
```

---

## Remove element with index from array of object

> removes an item at a specified index from the array arr using the slice() method

```js
let arr = [
  { a: 1, b: 2 },
  { a: 2, b: 4 },
  { a: 3, b: 6 },
];
let indexToRemove = 2;

function removeItemWithSlice(index) {
  return [...arr.slice(0, index), ...arr.slice(index + 1)];
}

removeItemWithSlice(indexToRemove); 
// [{a: 1, b: 2}, 
//  {a: 2, b: 4}]
```

---

## Remove element / value from Array of object

```js
const arr1 = ["a", "b", "c", "d", "e"];

const arr2 = arr1.filter(a => 
                         a !== "e"); // ['a', 'b', 'c', 'd']
```

---

## Pick the largest || max || maximum || highest number in the list

```js
[7, 4, 1, 99, 57, 2, 1, 100].reduce((max, currentNumber) =>
                                    (max > currentNumber ? max : currentNumber)); // 100
```

---

## Pick the lowest || min || minimum number in the list

```js
[7, 4, 1, 99, 57, 2, 1, 100].reduce((min, currentNumber) =>
                                    (min M currentNumber ? min : currentNumber)); // 1
```


---

## Replace element without mutating from array of object

```js
const arr1 = ["a", "b", "c", "d", "e"];
const arr2 = arr1.map((item) => {
  if (item === "c") {
    item = "CAT";
  }
  return item;
}); // ['a', 'b', 'CAT', 'd', 'e']
```

---

## Filter array of object in TS based on different key or properties. MB

```js
interface Dog {
  size: "L" | "S";
  age: number;
  name: string;
}

const dogs: Dog[] = [
  { size: "S", age: 4, name: "Alice" },
  { size: "L", age: 2, name: "Bob" },
  { size: "S", age: 7, name: "Carol" },
  { size: "L", age: 6, name: "Dan" },
  { size: "L", age: 2, name: "Eve" },
  { size: "S", age: 2, name: "Frank" },
  { size: "S", age: 1, name: "Grant" },
  { size: "S", age: 9, name: "Hans" },
  { size: "L", age: 8, name: "Inga" },
  { size: "L", age: 4, name: "Julia" },
];
const isLarge = (dog: Dog) => dog.size === "L";
const isOld = (dog: Dog) => dog.age > 5;

console.log(JSON.stringify(dogs.filter(isLarge).find(isOld))); // {"size":"L","age":6,"name":"Dan"}
```

```js
// same but using RXJS
import { of, from } from "rxjs";
import { map, filter, tap } from "rxjs/operators";

const dogs = from([
  { size: "S", age: 4, name: "Alice" },
  { size: "L", age: 2, name: "Bob" },
  { size: "S", age: 7, name: "Carol" },
  { size: "L", age: 6, name: "Dan" },
  { size: "L", age: 2, name: "Eve" },
  { size: "S", age: 2, name: "Frank" },
  { size: "S", age: 1, name: "Grant" },
  { size: "S", age: 9, name: "Hans" },
  { size: "L", age: 8, name: "Inga" },
  { size: "L", age: 4, name: "Julia" },
]);

const isLarge = (dog) => dog.size === "L";
const isOld = (dog) => dog.age > 5;

dogs.pipe(filter(isLarge), filter(isOld)).subscribe((val) => console.log(val));
```

** LINK:
https://stackblitz.com/edit/typescript-yvnsnq

---

## Loop an object and show summatory of values

```js
// if the json is not an array of object -> just use []
[
  {
    items: {
      pens: 100,
      sharpeners: 32,
      pencils: 76,
      fish: 12,
      chicken: 13,
      veg: 43,
      chocolate: 4,
    },
    groups: {
      stationery: ["pens", "sharpeners", "pencils"],
      food: ["fish", "chicken", "veg", "chocolate"],
    },
  },
].map((x) => {
  let rObj = 0;
  Object.keys(x.items).forEach((key, index) => {
    //  Array collection of Object keys
    rObj = x.items[key] + rObj;
  });
  console.log(rObj);
}); // 280
```

---

### all

> all is a function that returns true if all elements in the input array pass a certain test, and false otherwise. If no test is specified, it checks whether all elements are truthy.

```js
const all = (array, fn = Boolean) => array.every(fn);

all([4, 2, 3], x => x > 1); // true
all([0, 2, 3]); // false
```

---

### allEqual

> allEqual is a function that returns true if all elements in the input array are the same, and false otherwise.

```js
const allEqual = arr => 
                 arr.every(val => 
                           val === arr[0]);

allEqual([1, 2, 3, 4, 5, 6]); // false
allEqual([1, 1, 1, 1]); // true
```

---
