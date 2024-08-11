# `Better ifs`

- Why?

* Imperative programming is not bad or an anti-pattern. This is simply another way of achieving the same result
* As if/else blocks get bigger and/or nested they get harder to follow.
* This tends to encourage you to write a flexible, well organised and even object-oriented code

---
## undefined, null, 0, false, NaN, empty string check

```js
// bad
if (test1 !== null || test1 !== undefined || test1 !== "") {
  let test2 = test1;
}

// better
let test2 = test1 || "";
```

---
### Judgment simplification

> Use '.includes()' method instead of multiple 'if()'

```js
// ❌ instead of 💩
if (a === undefined || a === 10 || a=== 15 || a === null) { 
   //
} 

// better do
if ([undefined, 10, 15, null].includes(a)) {
  //
}
```

```js
// ❌ instead of 💩
const n = 1;
if (n === 1 || n === 2 || n === 3 || n === 4 || n === 5) {
  console.log('test');
}

const n = 1
const conditions = [ 1, 2, 3, 4, 5 ];
if (conditions.includes(n)) {
  console.log('test'); 
}
```


```js
const isVowel = (letter) => {

}
```

---

## Conditional Object key

```js
let condition = true;

const man = {
  someProperty: "some value",
  // the parenthesis will execute the ternary that will
  // result in the object with the property you want to insert
  // or an emtpy object. Then its content is spreaded in the wrapper object
  ...(condition === true ? {newProperty: "value"} : {})
}
```


---

### AND(&&) Short circuit evaluation

```js
// instead of  💩
if (isLoggedin) {
 goToHomepage(); 
} 

// better do 
isLoggedin && goToHomepage();
```


---

### Assigning default value and ||

```js
// instead of  💩
let imagePath; 
let path = getImagePath(); 
if(path !== null && path !== undefined && path !== '') { 
  imagePath = path; 
} else { 
  imagePath = 'default.jpg'; 
} 

// better do 
let imagePath = getImagePath() || 'default.jpg';
```

---

### null, undefined and ''

```js
// Longhand
let str = ''
let finalStr

if (str !== null && str !== undefined && str != '') {
  finalStr = str
} else {
  finalStr = 'default string'
}

// Shorthand
let str = ''
let finalStr = str || 'default string' // 'default string
```

---

### Using Optional `&&` chaining on functions

```js
// ❌ instead of 💩
// Using if-statement
if (someFunction) {
  some Function();
}
```

```js
// Better do ✅
// Using short-circuit
someFunction && someFunction();
```

```js
// Even better do ✅
// Using optional chaining
some Function?.();
```

---

###  use the `&&` operator to simplify your code

```js
// ❌ instead of 💩
const a = -1
const b = 101
const c = 10
const fn = () => {
  console.log('fatfish')
}

if (a < 0 && b > 100 && c === 10) {
  fn() // fatfish
}
```

```js
// Better do ✅
const a = -1
const b = 101
const c = 10
const fn = () => {
  console.log('fatfish')
}

a < 0 && b > 100 && c === 10 && fn(); // fatfish
```

---

###  A lot of nested "if...else".

```js
// ❌ instead of 💩
const checkFruits = (fruit, price) => {
  const blueFruits = [ 'Blueberry', 'juice indigo', 'oregon grape' ]
  if (fruit) {
    if (blueFruits.includes(fruit)) {
      console.log('blue')
      if (price > 100) {
        console.log('costly')
      }
    }
  } else {
    console.log('No fruit!')
  }
}

checkFruits('') // No fruit!
checkFruits('Blueberry') // blue
checkFruits('juice indigo', 200) // blue, costly
```

```js
// Better do ✅
const checkFruits = (fruit, price) => {
  const blueFruits = [ 'Blueberry', 'juice indigo', 'oregon grape' ]
  if (!fruit) {
    return console.log('No fruit!')
  }
  if (!blueFruits.includes(fruit)) {
    return
  }
  console.log('blue')
  if (price > 100) {
    console.log('costly')
  }
}

checkFruits('') // No fruit!
checkFruits('Blueberry') // blue
checkFruits('juice indigo', 200) // blue, costly
```

---

### from switch to function

```js
// ❌ instead of 💩
function getHexColor(car) {
  switch (car.color) {
    case Color.RED:
      return '#ff0000';
    case Color.GREEN:
      return '#00ff00';
    case Color.BLUE:
      return '#0000ff';
  }
}

// Better do ✅
function getHexColor(car) {
  let hexColors= {
    [Color.RED]: '#ff0000',
    [Color.GREEN]: '#00ff00',
    [Color.BLUE]: '#0000ff',
  };

  return hexColors[car.color];
}
```

---
### Check if a Property Exists in an Object

```js
const car = {
  engine: "2JZ-GTE",
  doors: 2,
};

console.log("doors" in car); // Result: true
console.log("manufacturer" in car); // Result: false
// This returns whether the property exists or not,
// not the value of it
```

---
### Use object instead of "switch"

```js
// ❌ instead of 💩
const n = 1;

let result;
switch (n) {
  case 1:
    result = "res-1";
    break;
  case 2:
    result = "res-2";
    break;
  case 3:
    result = "res-3";
    break;
}
```

```js
// Better do ✅
const n = 1;
const nMap = {
  1: "res-1",
  2: "res-2",
  3: "res-3",
};
const result = nMap[n];
```

---

### Multiple ifs conditions

```js
// ❌ instead of 💩
if (age >= 18 && follwers >= 100 && (origin === 'Sweden' || origin === 'Switzerland' || 'Latvia')) {
  // ...
}
```

```js
// better do
const checkCanApplyMPP = (options) => {
  const { age, follwers, origin } = options
  const canApplyMPP = age >= 18 && follwers >= 100 && [ 'Sweden', 'Switzerland', 'Latvia' ].includes(origin)
  
  return canApplyMPP
}

if (checkCanApplyMPP({ age: 18, follwers: 99, origin: 'Sweden' })) {
  // ...
}
```

---
### USE .INCLUDES TO CHECK FOR MULTIPLE CRITERIA

```js
// ❌ instead of 💩
let canEat = false;
if (fruit = 'apple' II fruit 'strawberry' || fruit "orange') {
  canEat true;
}

// Better do ✅
let canEat = false;
const eatables = ["apple", "strawberry", "orange", "cherry", "banana"];
if (eatables.includes(fruit)) {
  canEat = true;
}
```

---

### Use `object` instead `switch/case`

```js
// ❌ instead of 💩
switch (status) {
  case "success":
    return handlePayment();
  case "failed":
    return handleFailure();
  case "pending":
    return handlePending();
  default:
    throw Error("Status not recognized");
}
```

```js
// Better do ✅
const handlePayment = () = { /*e do stuff */ };
const handleFailure = () = { /*e do stuff */ };
const handlePending () = { /* do stuff */ };

const handlers = {
  success: handlePayment,
  failed: handleFailure,
  pending: handlePending,
}

const handler handlers[status];
if (!handler) throw Error('Status not recognized');
return handler();
```

```js
// ❌ instead of 💩
const getPriceByName = (name) => {
  if (name === '🍔') {
    return 30
  } else if (name === '🍨') {
    return 20
  } else if (name === '🍿') {
    return 10
  }
}
console.log(getPriceByName('🍔')) // 30
```

```js
// better do
const getPriceByName = (name) => {
  const foodMap = {
    '🍔': 30,
    '🍨': 20,
    '🍿': 10,
    // You can add new food here
    // ...
  }
  return foodMap[ name ]
}
console.log(getPriceByName('🍔')) // 30
```

---

### `early return` pattern: `if (!`

With the early return pattern, `we check for the opposite of the thing you want`, and return early to end the function when that's the case.

This `reduces nested if statements`, and makes your code a bit easier to read.


```js
// ❌ instead of 💩
function isValidUser(user) {
  if (isValidEmail(user.email)) {
    const alreadyRegistered = findUserByEmail(user.email);

    if (!alreadyRegistered) {
      return true;
    } else {
      return false;
    }
  } else {
    return false;
  }
}
```

```js
// better do
function isValidUser(user) {
  if (!isValidEmail(user.email)) return false;

  return findUserByEmail(user.email);
}
```

```js
// ❌ instead of 💩
function handleClick (event) {
  // Make sure clicked element has the .save-data class
  if (event.target.matches('.save-data')) {
    let id = event.target.getAttribute('data-id');
  }
}
```

```js
// Better do ✅
function handleClick (event) {
  if (!event.target.matches('.save-data')) return;
    let id = event.target.getAttribute('data-id');
  }
}
```

```js
// ❌ instead of 💩
function willItBlend(someObject) {
  if (
    typeof someObject !== 'object' ||
    someObject.blendable !== 'It will blend'
    ) {
    return false;
  }

  return true;
}
```

```js
// Better do ✅
function willItBlend(someObject) {
  return typeof someObject !== 'object' || someObject.blendable !== 'It will blend' ? false : true;
}
```


```js
// ❌ instead of 💩
onBackButtonClick(): void {
  if (!this.appBar?.onClick) return;
  this.appBar.onClick();
}

// Better do ✅
// use guards
onBackButtonClick(): void {
  !!this.appBar && this.appBar.onClick();
}
```


```js
// ❌ instead of 💩
function setAge(age) {
  if (!age) {
    return;
  }
  this.age = age;
}

// Better do ✅
// in this case is a single object
function setAge(age) {
  if (age) {
    this.age = age;
  }
}
```

---

## Use Early Returns & Align the Happy Path Left

> You want your happy path to be left-aligned, meaning it shouldn’t be buried deep within if-else statements.

> Keeping the happy path aligned to the left allows other engineers to quickly skim the code and grasp the function’s purpose more effectively. One effective way to achieve this is by using early returns.

```js
// instead of
function handleRequest(request) {
    if (request.isAuthorized) {
        if (request.hasValidData) {
            if (processRequest(request)) {
                return "Request processed successfully!";
            } else {
                return "Failed to process request.";
            }
        } else {
            return "Invalid data.";
        }
    } else {
        return "Unauthorized request.";
    }
}

// better do
function handleRequest(request) {
    if (!request.isAuthorized) {
        return "Unauthorized request.";
    }

    if (!request.hasValidData) {
        return "Invalid data.";
    }

    if (!processRequest(request)) {
        return "Failed to process request.";
    }

    // Happy path
    return "Request processed successfully!";
}

```

---

## Avoid Double negation logic

> Double Negation: isNotInactive (confusing because it involves two negatives: "not" and "inactive"). Positive Name: isActive (clear and easy to understand)

> Simplify Boolean Logic by Applying `De Morgan's Laws`: 
```js
!(A && B) is equivalent to !A || !B
!(A || B) is equivalent to !A && !B
```

```js
// instead of
if (!(!isVerified || !hasPermission)) {
    // Perform action
}

//better do
const isUserVerified = isVerified;
const hasUserPermission = hasPermission;

if (isUserVerified && hasUserPermission) {
    // Perform action
}

const isUserVerified = isVerified;
const hasUserPermission = hasPermission;

if (isUserVerified && hasUserPermission) {
    // Perform action
}
```



---

### Reactive ifs. MB

```js
// ❌ instead of 💩
of(1, 2, 3, 4)
  .pipe(map((n) => n * 3))
  .subscribe((n) => {
    if (n % 2 === 0) {
      console.log(n);
    }
  });
```

```js
// Better do ✅
of(1, 2, 3, 4)
  .pipe(
    map((n) => n * 3),
    filter((n) => n % 2 === 0)
  )
  .subscribe(console.log);
```

- Now this has several advantages:

* Looks clearer
* No clutter in the subscribe method
* Expressed entirely in the Rx language

> As a rule of thumb, if you see an if statement in the subscribe callback, think about the filter operator.

---

### Reactive if-else. MB

I have to do different things with odd and even numbers, I would have to write an if statement, right?". But the answer is still no. At first sight this may seem like a lot trouble to do for just removing an if-else statement, but in reality, this solution is far more explicit. Whenever anyone sees the partition function, it will become obvious to them that the Observable stream is going to be split in half, and the condition by which it is split is readily available and easy to find.

```js
// ❌ instead of 💩
of(1, 2, 3, 4)
  .pipe(map((n) => n * 3))
  .subscribe((n) => {
    if (n % 2 === 0) {
      console.log("Even number:", n);
    } else {
      console.log("Odd number", n);
    }
  });
```

```js
// instead do
const [evens, odds] = partition(
  of(1, 2, 3, 4).pipe(map((n) => n * 3)),
  (n) => n % 2 === 0
);

evens.subscribe((n) => console.log("Even number:", n));
odds.subscribe((n) => console.log("Odd number", n));
```

---

### switch old-school switch / no switch

```js
// ❌ instead of 💩
function counter(state = 0, action) {
  switch (action.type) {
    case "INCREMENT":
      return state + 1;
    case "DECREMENT":
      return state - 1;
    default:
      return state;
  }
}
```

```js
// Better do ✅
const counter = (state = 0, action) =>
  action.type === "INCREMENT"
    ? state + 1
    : action.type === "DECREMENT"
    ? state - 1
    : state;
```

---

### If Shortcut Notations

```js
// ❌ instead of 💩
let direction;
x = 1;
if (x > 100) {
  direction = 2;
} else {
  direction = 3;
}
```

```js
// Better do ✅
x = 1;

var direction = 1 > 100 ? console.log(2) : console.log(3);
```

---

### switch old-days school

```js
var day;
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
    day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
}

// FP good times
const getDay = switchcase({
  0: "Sunday",
  1: "Monday",
  2: "Tuesday",
  3: "Wednesday",
  4: "Thursday",
  5: "Friday",
  6: "Saturday",
})("Unknown");
const getCurrentDay = () => getDay(new Date().getDay());
const day = getCurrentDay();
```

---

### switch and cases with concatanation from old-school

```js
// ❌ instead of 💩
const doubler = (input) => {
  switch (typeof input) {
    case "number":
      return input + input;
    case "string":
      return input
        .split("")
        .map((letter) => letter + letter)
        .join("");
    case "object":
      Object.keys(input).map((key) => (input[key] = doubler(input[key])));
      return input;
    case "function":
      input();
      input();
  }
};
console.log(doubler([5, "hello"]));
```

```js
// Better do ✅
// no switch :)
const doubler = (input) => {
  return doubler.operationsByType[typeof input](input);
};
doubler.operationsByType = {
  number: (input) => input + input,
  string: (input) =>
    input
      .split("")
      .map((letter) => letter + letter)
      .join(""),
  function: (input) => {
    input();
    input();
  },
  object: (input) => {
    Object.keys(input).map((key) => (input[key] = doubler(input[key])));
    return input;
  },
};
console.log(doubler([5, "hello"]));
```

---

### a multiple function call using switch

```js
// ❌ instead of 💩
switch (something) {
  case 1:
    doX();
    break;
  case 2:
    doY();
    break;
  case 3:
    doN();
    break;
}
```

```js
// Better do ✅
var cases = {
  1: doX,
  2: doY,
  3: doN,
};
if (cases[something]) {
  cases[something]();
}
```

---

### Imperative -> Declarative

> Emphasis on explicit control flow is what differentiates imperative programming from declarative programming.

```js
// ❌ instead of 💩
isAuthenticated$ = selectAuthentication().pipe(
  tap((auth) => {
    if (isAuthenticated) {
      router.navigate("/home");
    } else {
      router.navigate("/login");
    }
  })
);

const isAuthenticatedSub = isAuthenticated$.subscribe();
```

```js
// Better do ✅
const isAuthenticated$ = selectAuthentication()
    .pipe(filter(auth => auth), tap(_ => router.navigate('/home'));
const isNotAuthenticated$ = selectAuthentication()
    .pipe(filter(auth => !auth), tap(_ => router.navigate('/login'));
const authSub = merge(isAuthenticated$, isNotAuthenticated$)
    .subscribe();
```

---

### Default parameter value shorthand

```js
// ❌ instead of 💩
function volume(l, w, h) {
  if (w === undefined) w = 3;
  if (h === undefined) h = 4;
  return l * w * h;
}
console.log(volume(2)); // 24
```

```js
// Better do ✅
volume = (l, w = 3, h = 4) => l * w * h;

console.log(volume(2)); // 24
```

---

### if all checks: `!== null` && `!== undefined` && `!== ''` or else

```js
// ❌ instead of 💩
let finalName;
let name = "";
if (name !== null && name !== undefined && name !== "") {
  finalName = name;
} else {
  finalName = "Leo";
}

console.log(finalName); // Leo
```

```js
// Better do ✅
let name = "";
let finalName = name || "Leo";

console.log(finalName); // Leo
```

---

### Multiples ifs `=== && ||` same variable

```js
// ❌ instead of 💩
if (value === 1 || value === "one" || value === 2 || value === "two") {
  //Do something....
}
```

```js
// Better do ✅
if ([1, "one", 2, "two"].indexOf(value) >= 0) {
  //Do something....
}
```

```js
// or even better
if ([1, "one", 2, "two"].includes(value)) {
  //Do something....
}
```

---

### Replace switch using OOP way

```js
// ❌ instead of 💩
const animal = new Animal();

switch (animal.getType()) {
  case IS_DOG:
    console.log("Woof!");
    break;
  case IS_CAT:
    console.log("Meow!");
    break;
}
```

```js
// Better do ✅
const IS_DOG = "dog"
const IS_CAT = "cat"

class Animal {

    constructor(
        private type: string
    ){}

    getType(): string {
        return this.type
    }

    bark() {
        console.log("Woof!")
    }

    meow() {
        console.log("Meow!!!")
    }
}

function speak(animal: Animal) {
    const theIndex = {
        [IS_DOG]: animal.bark.bind(animal),
        [IS_CAT]: animal.meow.bind(animal)
    }

    theIndex[animal.getType()] ? theIndex[animal.getType()]() : console.log("unknown animal")
}

const animal = new Animal(IS_DOG);
speak(animal)
```

---

### Check if object is empty

```js
Object.keys({}).length // 0
Object.keys({key: 1}).length // 1 
```

---

### Check Array is NOT EMPTY. MB

```js
const arr = [];
const arr2 = [1, 2, 3];

const isNotEmpty = (arr) => Boolean(arr?.length);

isNotEmpty(arr); // false
isNotEmpty(arr2); // true
```

---

### Don't Use If-Else + Switch: Use Object Literals / coke case

```js
// ❌ instead of 💩
function getTranslation(rhyme) {
  if (rhyme.toLowerCase() === "apples and pears") {
    return "Stairs";
  } else if (rhyme.toLowerCase() === "hampstead heath") {
    return "Teeth";
  } else if (rhyme.toLowerCase() === "loaf of bread") {
    return "Head";
  } else if (rhyme.toLowerCase() === "pork pies") {
    return "Lies";
  } else if (rhyme.toLowerCase() === "whistle and flute") {
    return "Suit";
  }
  return "Rhyme not found";
}

getTranslation("apples and pears"); // "Stairs"

// Better do ✅
function getTranslationMap(rhyme) {
  const rhymes = {
    "apples and pears": "Stairs",
    "hampstead heath": "Teeth",
    "loaf of bread": "Head",
    "pork pies": "Lies",
    "whistle and flute": "Suit",
  };
  return rhymes[rhyme.toLowerCase()] ?? "Rhyme not found";
}

getTranslationMap("apples and pears"); // "Stairs"
```

```js
const extensionTwo = '.js';

const extensionObject = {
  '.css': 'text/css',
  '.js': 'text/javascript',
  '.json': 'application/json',
  '.html': 'text/html',
}

console.log(extensionObject[extensionTwo] || extensionObject['.html'])    // "text/javascript"
```

---

### Conditional 2 evaluation and a return x2

```js
// ❌ instead of 💩
if (this.state.data) {
  return this.state.data;
} else {
  return "Fetching Data";
}
```

```js
// Better do ✅
return this.state.data || "Fetching Data";
```

---

## The logical assignment operator `&&=` MB

If the first variable is truthy, then the logical operator &&= assigns the second variable to it. So the logical operator &&= allows us to achieve the same thing with a shorter syntax.

```js
// ❌ instead of 💩
let firstOne = 15;
let secondOne = 22;

if (firstOne) {
  firstOne = secondOne;
}
console.log(firstOne); // 22
```

```js
// just do
let firstOne = 15;
let secondOne = 22;

firstOne &&= secondOne; // 22
```

---

## The logical assignment operator `||=`. MB

Since the variable firstOne is falsy(null), the variable secondOne gets assigned to it.

```js
// ❌ instead of 💩
let firstOne = null;
let secondOne = 22;

if (!firstOne) {
  firstOne = secondOne;
}
console.log(firstOne); // 22
```

```js
let firstOne = null;
let secondOne = 22;

firstOne ||= secondOne; // 22

let firstOne = undefined;
let secondOne = 23;

firstOne ||= secondOne; // 23
```

---

### The logical operator `??=`. MB

`??=` changes the value only if it's null or undefined.

```js
// ❌ instead of 💩
let firstOne = undefined;
let secondOne = 123;

if (firstOne === null || firstOne === undefined) {
  firstOne = secondOne;
}
console.log(firstOne); // 123
```

```js
// Better do ✅
let firstOne = null;
let secondOne = 123;

firstOne ??= secondOne; // 123

// also works with undefined
let firstOne = undefined;
let secondOne = 123;

firstOne ??= secondOne; // 123
```

---

### The nullish coalescing operator `??`. MB

`??` returns the first argument if it's `not null/undefined`. Otherwise, the second one.

```js
// ❌ instead of 💩
result = 1 !== null && 1 !== undefined ? 1 : 3; // 1
```

```js
// Better do ✅
result = 1 ?? 3; // 1
```

---

## Short-circuit Evaluation using ternary approach. 1 if and same value return

```js
// ej1
// ❌ instead of 💩
let dbHost;

if (process.env.DB_HOST) {
  dbHost = process.env.DB_HOST;
} else {
  dbHost = "localhost";
}
```

```js
// Better do ✅
const dbHost = process.env.DB_HOST || "localhost";
```

```js
// ej2
// ❌ instead of 💩
// Original IF..ELSE statement
let isEven = "";

if (variable % 2 == 0) {
  isEven = "yes";
} else {
  isEven = "no";
}
```

```js
// Better do ✅
// ternary operators
let isEven = variable % 2 == 0 ? "yes" : "no";
```

```js
// ej3
// ❌ instead of 💩
var direction;

if (x > 100) {
  direction = 1;
} else {
  direction = -1;
}
```

```js
// Better do ✅
const direction = x > 100 ? 1 : -1;
```

---

## ternary operators

```js
const errorCode = 200;
let message = null;

if (errorCode > 299) {
  m
} else {
  message = "Everything is alright";
}
```

```js
const errorCode = 200;
const message = errorCode > 299
  ? "Something went wrong"
  : "Everything is alright";
```

---

## Boolean && Func()

```js
// ❌ instead of 💩
const amenities = []

if (hasToilet) {
  amenities.push('Toilet')
}

if (hasKitchen) {
  amenities.push('Kitchen')
}

if (hasWifi) {
  amenities.push('Wi-Fi')
}

// better do 
const amenities = [];
hasToilet && amenities.push("Toilet");
hasKitchen && amenities.push("Kitchen");
hasWifi && amenities.push("Wi-Fi");
```

---

### Ternary expression `?`: Instead of `if... else...` better do `? ... : ...`

```js
// ❌ instead of 💩
const n = 18;
let result;
if (n % 2 === 0) {
  result = "even number";
} else {
  result = "odd number";
}

// better do
const n = 18;
let result = n % 2 === 0 ? "even number" : "odd number";
```

---

### Ternary expression: Use "+" to convert string to number

```js
// ❌ instead of 💩
let str = "123";
let num = Number(str); // 123
let num2 = parseInt(str); // 123

// better do
let str = "123";
let num = +str; // 123
```

---

### != null, !== undefined, variable1 !== ''

```js
// ❌ instead of 💩
if (variable1 !== null || variable1 !== undefined || variable1 !== "") {
  let variable2 = variable1;
}

// Better do ✅
const variable2 = variable1 || "new";
```

```js
let variable1;
let variable2 = variable1 || "bar";
console.log(variable2 === "bar"); // true
```

```js
variable1 = "foo";
variable2 = variable1 || "bar";
console.log(variable2); // foo
```

---

### Object [key] Shorthand. 2if and 3returns

```js
// ❌ instead of 💩
function validate(values) {
  if (!values.first) return false;
  if (!values.last) return false;
  return true;
}

console.log(validate({ first: "Bruce", last: "Wayne" })); // true

// Better do ✅
// object validation rules
const schema = {
  first: {
    required: true,
  },
  last: {
    required: true,
  },
};

// universal validation function
const validate = (schema, values) => {
  for (field in schema) {
    if (schema[field].required) {
      if (!values[field]) {
        return false;
      }
    }
  }
  return true;
};

console.log(validate(schema, { first: "Bruce" })); // false
console.log(validate(schema, { first: "Bruce", last: "Wayne" })); // true
```

---

### multiple if & nested if-else

```js
if (this.client.isM) {
  if (this.wishlist.qty !== 0 && this.basket.qty !== 0) {
    return "right-7";
  } else if (this.basket.qty !== 0 || this.wishlist.qty !== 0) {
    return "right-4";
  } else {
    return "right-2";
  }
} else {
  return "right-4";
}
```

```js
// Better do ✅ : declarative & functional
const validate1 = this.wishlist.qty !== 0 && this.basket.qty !== 0;
const validate2 = this.basket.qty !== 0 || this.wishlist.qty !== 0;

const ifValidation1 = (y) =>
  validate1 ? "right-7" : validate2 ? "right-4" : "right-2";
const ifValidation2 = (x) => (this.client.isM ? ifValidation1 : "right-4");
```

---

### Asigning to `same variable` depending on `1 desition`

```js
if (type === "budgets") {
  let desc = this.budgets[optionSelected];
} else {
  let desc = this.sizes[optionSelected];
}
```

```js
// Better do ✅
const types = (type) =>
  type === "budgets"
    ? this.budgets[optionSelected]
    : this.sizes[optionSelected];
```

---

### Based on a `function return` assign another string `value`. Assigning default value

```js
// insted of
let imagePath;
let path = getImagePath();

if (path !== null && path !== undefined && path !== "") {
  imagePath = path;
} else {
  imagePath = "default.jpg";
}
```

```js
// Better do ✅
let imagePath = getImagePath() || "default.jpg";
```

---

### Short circuit evaluation: `AND(&&)`. MB

```js
// Instrad of
if (isLoggedin) {
  goToHomepage();
}

// Better do ✅
isLoggedin && goToHomepage();
```

---

### Multiple condition checking

```js
// ❌ instead of 💩
if (value === 1 || value === "one" || value === 2 || value === "two") {
  // Execute some code
}

// Better do ✅
if ([1, "one", 2, "two"].includes(value)) {
  // Execute some code
}
```

---

### Make it sound like a question not statement

```js
// ❌ instead of 💩
const numbers = [1,2,3,4];

// `even` Reads like a statement
const even = num => num % 2 === 0);
numbers.filter(even);
```

```js
// Better do ✅
const numbers = [1,2,3,4];

// `isEven` Reads like a question
const isEven = num => num % 2 === 0);
numbers.filter(isEven);
```

---

### return `true` / return `false` same function

```js
// ❌ instead of 💩
const isPet = (animal) => {
  if (animal === "cat" || animal === "dog") {
    return true;
  }
  return false;
};
```

```js
// Better do ✅
const isPet = (animal) => {
  const pets = ["cat", "dog", "snake", "bird"];

  return pets.includes(animal);
};
```

---

### Using Array.every

```js
// ❌ instead of 💩
const pets = [
  { name: "cat", nLegs: 4 },
  { name: "snake", nLegs: 0 },
  { name: "dog", nLegs: 4 },
  { name: "bird", nLegs: 2 },
];
const check = (pets) => {
  for (let i = 0; i < pets.length; i++) {
    if (pets[i].nLegs != 4) {
      return false;
    }
  }
  return true;
};
check(pets); // false
```

```js
// Better do ✅
let areAllFourLegs = pets.every((p) => p.nLegs === 4); // false
```

---

## Using Indexing Instead of switch...case

```js
// ❌ instead of 💩
const getBreeds = (pet) => {
  switch (pet) {
    case "dog":
      return ["Husky", "Poodle", "Shiba"];
    case "cat":
      return ["Korat", "Donskoy"];
    case "bird":
      return ["Parakeets", "Canaries"];
    default:
      return [];
  }
};

let dogBreeds = getBreeds("dog"); //['Husky', 'Poodle', 'Shiba']
```

```js
// Better do ✅
const breeds = {
  dog: ["Husky", "Poodle", "Shiba"],
  cat: ["Korat", "Donskoy"],
  bird: ["Parakeets", "Canaries"],
};
const getBreeds = (pet) => {
  return breeds[pet] || [];
};

let dogBreeds = getBreeds("cat"); //['Korat', 'Donskoy']
```

---

## Simplifiesd coke example

```js
// ❌ instead of 💩
const n = 1
let result
switch (n) {
  case 1:
    result = 'res-1'
    break
  case 2:
    result = 'res-2'
    break
  case 3:
    result = 'res-3'
    break  
  // ...There are a lot more
}


// better do
const n = 1;
const nMap = {
  1: 'res-1',
  2: 'res-2',
  3: 'res-3'
}
const result = nMap[n]; // res-1


// even better
const n = 1;
const results: { [key: number]: string } = {
  1: 'res-1',
  2: 'res-2',
  3: 'res-3',
}

const result = results[n] ?? 'default'
```

---

## Replacing switch statements with Object literals. Coke example

```js
// coke classic
type DrinkType = 'coke' | 'pepsi' | 'lemonade'

const drinkTypes: { [key in DrinkType]: string } = {
  coke: 'Coke',
  pepsi: 'Pepsi',
  lemonade: 'Lemonade',
}

const getDrink = (type: DrinkType) => `The drink I chose was ${drinkTypes[type]}`

console.log(getDrink('pepsi'))
```

```js
// ej1
function getDrink(type) {
  return (
    "The drink I chose was " +
    {
      coke: "Coke",
      pepsi: "Pepsi",
      lemonade: "Lemonade",
    }[type]
  );
}
getDrink("pepsi");
```

```js
// ej2
function getDrink(type) {
  var drinks = {
    coke: function () {
      return "Coke";
    },
    pepsi: function () {
      return "Pepsi";
    },
    lemonade: function () {
      return "Lemonade";
    },
    default: function () {
      return "Default item";
    },
  };
  return (drinks[type] || drinks["default"])();
}

getDrink("coke");
```

```js
// ej3
function getSnack(type) {
  var snack;

  function isDrink() {
    return (snack = "Drink");
  }
  function isFood() {
    return (snack = "Food");
  }
  var snacks = {
    coke: isDrink,
    pepsi: isDrink,
    cookies: isFood,
    crisps: isFood,
  };

  return snacks[type]();
}

getSnack("coke"); // 'Drink'
```

```js
// Ej4
// even without ANY IF
function getDrink(type) {
  var drink;
  var drinks = {
    coke: function () {
      drink = "Coke";
    },
    pepsi: function () {
      drink = "Pepsi";
    },
    lemonade: function () {
      drink = "Lemonade";
    },
    default: function () {
      drink = "Default item";
    },
  };

  // invoke it
  (drinks[type] || drinks["default"])();
  return "The drink I chose was " + drink;
}
getDrink("coke"); // The drink I chose was Coke
```

```js
// ej5
function getDrink(type) {
  var drinks = {
    coke: function () {
      return "Coke";
    },
    pepsi: function () {
      return "Pepsi";
    },
    lemonade: function () {
      return "Lemonade";
    },
    default: function () {
      return "Default item";
    },
  };
  return (drinks[type] || drinks["default"])();
}

getDrink("coke"); // 'Coke'
```

* LINK<BR>
https://toddmotto.com/deprecating-the-switch-statement-for-object-literals/

---

## function factories

Functionality based on arguments passed across

```js
function hello(lang) {
  return function (firstname, lastname) {
    if (lang === "en") {
      console.log("Hello " + firstname + lastname);
    }
    if (lang === "es") {
      console.log("Hola " + firstname + lastname);
    }
  };
}

var en = hello("en");
var es = hello("es");

en("Leo", "Lanese"); // Hello LeoLanese
es("Leo", "Lanese"); // Hola LeoLanese
```

---

## Functions as Data: replacing multiple IF evaluations

```js
// instead
var calc = {
  run: function (op, n1, n2) {
    var result;
    if (op == "add") {
      result = n1 + n2;
    } else if (op == "sub") {
      result = n1 - n2;
    } else if (op == "mult") {
      result = n1 * n2;
    } else if (op == "div") {
      result = n1 / n2;
    }
    return result;
  },
};
calc.run("sub", 5, 3); //2

// better do ✅
var calc = {
  add : function(a,b) {
    return a + b;
  },
  sub : function(a,b) {
    return a - b;
  },
  mult : function(a,b) {
    return a *;
  },
  div : function(a,b) {
    return a / b;
  },
  run: function(fn, a, b) {
    return fn && fn(a,b); 
  }
}
calc.run(calc.mult, 7, 4); //28
```

---

## Switch shorthand (same code example)

```js
const dayNumber = new Date().getDay();
// Long-hand
let day;
switch (dayNumber) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
    day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
}
// Short-hand
const days = {
  0: "Sunday",
  1: "Monday",
  2: "Tuesday",
  3: "Wednesday",
  4: "Thursday",
  5: "Friday",
  6: "Saturday",
};
const day = days[dayNumber];
```

---

## Fallback values

```js
// Long-hand
let name;
if (user?.name) {
  name = user.name;
} else {
  name = "Anonymous";
}

// Short-hand
const name = user?.name || "Anonymous";
```

---

## Better ifs, Improving ifs, ifs improvements, Improve nested conditionals, better conditionals:

### Why?

As if/else blocks get bigger and/or nested they get harder to follow.
This tends to encourage you to write a flexible, well organised and even object-oriented code

```js
// ❌ instead of 💩
// Use Array.includes for Multiple Criteria
function test(fruit) {
  if (fruit == "apple" || fruit == "strawberry") {
    console.log("red");
  }
}
```

```js
// Better do ✅
function test(fruit) {
  // extract conditions to array
  const redFruits = ["apple", "strawberry", "cherry", "cranberries"];
  if (redFruits.includes(fruit)) {
    console.log("red");
  }
}
```

---

## Use Default Function Parameters and Destructuring

```js
function test(fruit, quantity) {
  if (!fruit) return;
  const q = quantity || 1; // if quantity not provided, default to one
  console.log(`We have ${q} ${fruit}!`);
}
//test results
test("banana"); // We have 1 banana!
test("apple", 2); // We have 2 apple!

// Better do ✅ :
// destructing - get name property only
// assign default empty object {}
function test({ name } = {}) {
  console.log(name || "unknown");
}
//test results
test(undefined); // unknown
test({}); // unknown
test({ name: "apple", color: "red" }); // apple
```

---

## Favor Object Literal than Switch Statement

```js
function test(color) {
  // use switch case to find fruits in color
  switch (color) {
    case "red":
      return ["apple", "strawberry"];
    case "yellow":
      return ["banana", "pineapple"];
    case "purple":
      return ["grape", "plum"];
    default:
      return [];
  }
}
//test results
test(null); // []
test("yellow"); // ['banana', 'pineapple']
```

```js
// Better do ✅
function test(color) {
  // use object literal to find fruits in color
  const fruitColor = {
    red: ["apple", "strawberry"],
    yellow: ["banana", "pineapple"],
    purple: ["grape", "plum"],
  };
  return fruitColor[color] || [];
}
```

```js
// even better do: .every()
const fruits = [
  { name: "apple", color: "red" },
  { name: "banana", color: "yellow" },
  { name: "grape", color: "purple" },
];
function test(myColor) {
  // condition: short way, all fruits must be red
  const isAllRed = fruits.every((f) => f.color === myColor);
  console.log(isAllRed); // false
}
```

```js
// even better do: .some()
const fruits = [
  { name: "apple", color: "red" },
  { name: "banana", color: "yellow" },
  { name: "grape", color: "purple" },
];
function test(myColor) {
  // condition: short way, all fruits must be red
  const isAllRed = fruits.some((f) => f.color === myColor);
  console.log(isAllRed); // true
}
```

---

## Replace old-style if with curry

```js
// instad of
// old-style if
const cases = new Object();
cases.property1 = 42;
function switchcase(cases, defaultCase, key) {
  if (cases.hasOwnProperty(key)) {
    return cases[key];
  } else {
    return defaultCase;
  }
}
switchcase(cases, "def", "property1"); // 42
```

```js
// Better do ✅
// curry, converting the if to a ternary and ES6 style (MB)
const cases = new Object();
cases.property1 = 42;

const switchcase = (cases) => (defaultCase) => (key) =>
  cases.hasOwnProperty(key) ? cases[key] : defaultCase;

switchcase(cases)("")("property1"); // 42
```

---

## function to return old- school ifs. Now, const with value

```js
function saveCustomer(x) {
  if (isCustomerValid(x)) {
    database.save(x);
  } else {
    alert("x is invalid");
  }
}
```

```js
// Better do ✅
const saveCustomer = (x) =>
  isCustomerValid(x) ? database.save(x) : alert("x is invalid");
```

---

## argument validation conditional

```js
// ❌ instead of 💩
var parm = "stranger";

if (theName) {
  parm = theName;
}
```

```js
// Better do ✅
var parm = theName || "stranger";
```

---

### for loops and ifs with push()

```js
// ❌ instead of 💩
const cats = [
  { name: "Mojo", months: 84 },
  { name: "Mao-Mao", months: 34 },
  { name: "Waffles", months: 4 },
  { name: "Pickles", months: 6 },
];
var kittens = [];

// poorly written `for loop`
for (var i = 0; i < cats.length; i++) {
  if (cats[i].months < 7) {
    kittens.push(cats[i].name);
  }
}
console.log(kittens);
```

```js
// Better do ✅
const isKitten = (cat) => cat.months < 7;
const getName = (cat) => cat.name;
const kittens = cats.filter(isKitten).map(getName);
```

```js
// 1: old school
let f = () => {
  console.log("test");
};

function ifVal(x, f) {
  if (x == null) {
    return null;
  } else {
    return f(x);
  }
}
ifVal(1, f); // test
```

```js
// ES6 & ternary operator
let f = () => {
  console.log("test");
};

const ifVal = (x, f) => (x == null ? null : f(x)); // test
```

```js
// old school else-if
function customerValidation(customer) {
  if (!customer.email) {
    return error("email is require");
  } else if (!customer.login) {
    return error("login is required");
  } else if (!customer.name) {
    return error("name is required");
  } else {
    return customer;
  }
}
```

```js
// ES6 style custom formatted ternary magic
```js
const customerValidation = customer =>
  !customer.email ? error('email is required')
  : !customer.login ? error('login is required')
  : !customer.name ? error('name is required')
  : customer
```

```js
// using no error Object literal validation using multi-action nested ternaries (object deep validation)
var obj = {};
// obj.foo = {"key":"value"}
// obj.foo.foo2 = {"key2":"value2"}

typeof obj === "undefined"
  ? false
  : typeof obj.foo === "undefined"
  ? false
  : typeof obj.foo.foo2 !== "undefined"
  ? console.log(true + "-" + Object.keys(obj.foo.foo2))
  : false;
```

—--

## if using ternary conditional

```js
// ❌ instead of 💩
if (isArthur) {
  weapon = "Excalibur";
} else {
  weapon = "katana";
}

// Better do ✅
const weapon = isArthur ? "Excalibur" : "Longsword";
```

```js
// ❌ instead of 💩
if (state.tracking.messageInfo.showHtml === 'true') {
  this.showHtml = true;
} else {
  this.showHtml = false;
}

// Better do ✅
this.showHtml = state.tracking.messageInfo.showHtml === 'true' ? true : false;
```

---

## Short if

```js
if (val) {
  return foo();
} else {
  return bar();
}
```

```js
// you can write this:
return val ? foo() : bar();
```

--—

## if null || empty

```js
// ❌ instead of 💩
if (y != null && y != "") {
}
```

```js
// Better do ✅
if (y) {
}
```

—

## Iterating over Node Lists

```js
// This is a ternary operator—works like an inline if-else statement
var b = typeof a === "number" ? a : 42;
```

```js
// ❌ instead of 💩
if (expr) {
  doSomething();
}
```

```js
// Better do ✅
expr && doSomething();
```

---

## ternary operator: x3

```js
isArthur && isKing ?
      function (){
        alert("Hail Arthur, King of the Britons!");
  	console.log("Current weapon: Excalibur");
        console.log('excalibur')
       }(); // call the Function expression
	:
	function (){
    	alert("Hail Arthur, King of the Britons!");
      console.log("Current weapon: Excalibur");
      console.log('excalibur')
	}(); // call the Function expression
```

```js
// another example
_.isEmpty($scope.myTheme[2])
  ? (function () {
      resetScheme();
    })()
  : (function () {
      resetScheme();
      paintScheme(elements);
    })();
```

---

## MULTIPLE ACTIONS IN TERNARIES = ()

Multiple params in shorthand if using: `(,)`

```js
isArthur && isKing
  ? ((weapon = 1), (helmet = 2))
  : ((weapon = 3), (helmet = 4));
```

---

## OR SIMPLE but effective

Replace if with Method lookups using Command Pattern:
"this serve the propouse of compare the same object again and again only"

```js
var color = "red";
if (color) {
  if (color === "black") {
    console.log("black");
  } else if (color === "red") {
    console.log("red");
  } else if (color === "blue") {
    console.log("blue");
  } else if (color === "green") {
    console.log("green");
  } else {
    console.log("yellow");
  }
}
```

```js
// Kind of better:
switch (color) {
  case "black":
    printBlackBackground();
    break;
  case "red":
    printRedBackground();
    break;
  case "blue":
    printBlueBackground();
    break;
  case "green":
    printGreenBackground();
    break;
  default:
    printYellowBackground();
}
```

```js
// Even better (if need extra parameters to verify):
switch (true) {
  case typeof color === "string" && color === "black":
    printBlackBackground();
    break;
  case typeof color === "string" && color === "red":
    printRedBackground();
    break;
  case typeof color === "string" && color === "blue":
    printBlueBackground();
    break;
  case typeof color === "string" && color === "green":
    printGreenBackground();
    break;
  case typeof color === "string" && color === "yellow":
    printYellowBackground();
    break;
}
```

// The FINAL better way: method lookup/command pattern: less procedural more object-oriented
When you deal with a switch, you're NOT likely to expect falling through 2 different cases.
Just like else if, you probably expect to execute one and only one case.

```js
function function4() {
  console.log("function4");
}
var color = "red";
if (color) {
  if (color === "black") {
    console.log("black");
  } else if (color === "red") {
    console.log("red");
  } else if (color === "blue") {
    console.log("blue");
  } else if (color === "green") {
    console.log("green");
  } else {
    console.log("yellow");
  }
}
```

```js
// or even Super better: "no IFS"
const red = () => "red";
const blue = () => "blue";
const yellow = () => "yellow";

function getColor(type) {
  var colors = {
    red: red,
    blue: blue,
    yellow: yellow,
    default: function () {
      return "Another color";
    },
  };
  return (colors[type] || colors["default"])();
}
getColor("red"); // red
```

---

### Another example

```js
if (name === "patrick") {
  sayHello();
} else if (name === "jane") {
  giveSomeNews();
} else {
  sayBye();
}

// Method lookup using Command pattern
function sayHello() {
  console.log("sayHello");
}

function giveSomeNews() {
  console.log("giveSomeNews");
}

function sayBye() {
  console.log("sayBye");
}

// change name to test:
var name = "patrick";
// var name = "jane";

var greetings = {
  patrick: the,
  john: giveSomeNews,
  jane: giveSomeNews,
};

// greetings[patrick] = sayHello is a function, Y: sayHello() N: sayBye()
// be aware that we always test the same greetins[n]
typeof greetings[name] === "function" ? greetings[name]() : sayBye();
```

---

## A MB getDrink implementation. The coke example

https://toddmotto.com/deprecating-the-switch-statement-for-object-literals/

```js
function getSnack(type) {
  var snack;

  function isDrink() {
    return (snack = "Drink");
  }

  function isFood() {
    return (snack = "Food");
  }

  var snacks = {
    coke: isDrink,
    pepsi: isDrink,
    cookies: isFood,
    crisps: isFood,
  };

  return snacks[type]();
}

var snack = getSnack("coke");
console.log(snack); // 'Drink'
```

```js
function getDrink(type) {
  var drink;
  var drinks = {
    coke: function () {
      drink = "Coke";
    },
    pepsi: function () {
      drink = "Pepsi";
    },
    lemonade: function () {
      drink = "Lemonade";
    },
    default: function () {
      drink = "Default item";
    },
  };

  // invoke it
  (drinks[type] || drinks["default"])();

  // return a String with chosen drink
  return "The drink I chose was " + drink;
}

var drink = getDrink("coke");
// The drink I chose was Coke
console.log(drink);
```

```js
coke = function () {
  alert("test");
};

function getDrink(type) {
  var drinks = {
    coke: function () {
      return "Coke";
    },
    pepsi: function () {
      return "Pepsi";
    },
    lemonade: function () {
      return "Lemonade";
    },
    default: function () {
      return "Default item";
    },
  };

  return (drinks[type] || drinks["default"])();
}

getDrink("coke"); // alert coke
```

---

## object deep validation

1.

```js
// ❌ instead of 💩
if (node && node.kids && node.kids[index]) {
  foo(node.kids[index]);
}

// Better do ✅
var kid = node && node.kids && node.kids[index];
if (kid) {
  foo(kid);
}
```


```js
// ❌ instead of 💩
if (node && node.kids && node.kids[index]) {
  foo(node.kids[index]);
}

// Better do ✅
var kid = node && node.kids && node.kids[index];
if (kid) {
  foo(kid);
}
```

```js
// instead of
// we validate the toConfirmEnRoute
if (gradeValue !== undefined && gradeValue !== null && gradeValue.length > 0) {
  console.log("IN");
}

// better do
// validate typeof
if (gradeValue && gradeValue.length > 0) {
  console.log("IN");
}
```

---

## Validate undefined & null & >0

```js
// instad of
if (gradeValue !== undefined && gradeValue !== null && gradeValue.length > 0) {
  console.log("IN");
}
```

```js
//better do: validate typeof
if (gradeValue && gradeValue.length > 0) {
  console.log("IN");
}
```

---

## Coercion to verify lack of existence:

```js
// ❌ instead of 💩
var oTest;
if (oTest !== undefined && oTest !== null && oTest !== 0) {
  console.warn("Showing the " + oTest); // Showing the 1 = is defined, not null and !=0
}
```

```js
// Better do ✅
var oTest;
if (oTest) {
  console.warn("Showing the " + oTest); // NOT ENTER because: oTest is undefined, not null and !=0
}
```

```js
//OR BETTER
var oTest;
if (oTest || oTest === 0) {
  console.log("something is there"); // a is something => !== undefined, !== null and !== ""
}
```

```js
// MAYbe also a better approach:
var s1 = { p2: "OK" };
function n(p1) {
  var nLocal = p1.s2 || "error";
  console.log(nLocal);
}
n(s1); // error
// function n will never execute without s1.p2
```

---

## Short Circuit Conditionals

1.

```js
// ❌ instead of 💩
if (available) {
  addToCart();
}
```

```js
// Better do ✅  use Short Circuit Conditionals
isValid();
```

```js
// ej2
// ❌ instead of 💩
if (this.affectedUsersPage.value.condition === 'everyone') {
    return true;
  } else {
   return (
     !!this.affectedUsers.payload['ipRange'] ||
     !!this.affectedUsers.payload['description'] ||
     !!this.affectedUsers.payload['emailAddress']
   );
  }
}
```

```js
// Better do ✅
isValid() {
  return this.affectedUsersPage.value.condition === 'everyone' ? true : (
    !!this.affectedUsers.payload['ipRange'] ||
    !!this.affectedUsers.payload['description'] ||
    !!this.affectedUsers.payload['emailAddress']
  );
}
```

---

## The Ternary operator: conditional ?: operator

// make an array of the args if any, or return empty array
var args = arguments ? toArray(arguments) : [];
// end game or go to next level
gameOver ? finally() : nextLevel();

---

## Better ifs: Function Delegation

```js
// 1
// instead of
function getEventTarget(evt) {
  if (!evt) {
    evt = window.event;
  }
  if (!evt) {
    return;
  }
  var target;
  if (evt.target) {
    target = evt.target;
  } else {
    target = evt.srcElement;
  }
  return target;
}
```

```js
// better do 
// Function Delegation:
function getEventTarget(evt) {
    return evt ? evt.target || evt.srcElement : null
}
```

```js
// 2
// instead of
function itemDropped(item, location) {
    if (!item) {
        return false;
    } else if (outOfBounds(location) {
        var error = outOfBounds;
        server.notify(item, error);
        items.resetAll();
        return false;
    } else {
        animateCanvas();
        server.notify(item, location);
        return true;
    }
}
```

```js
// better
// function delegation
function itemDropped(item, location) {
  const dropOut = function() {
    server.notify(item, outOfBounds);
    items.resetAll();
    return false;
  };
  const dropIn = function () {
    server.notify(item, location);
    animateCanvas();
    return true;
  };
  return !!item && (outOfBounds(location) ? dropOut() : dropIn());
}

// or
function itemDropped(item, location) {
    return !item ? false : 
    outOfBounds(location) ? (server.notify(item, outOfBounds), items.resetAll(), false) :
    (animateCanvas(), server.notify(item, location);
}
```

```js
// 3
// instead of
  writeValue(value: DateRangePickerEntryConfig): void {
    // Evaluate the rangeFn when control loaded with default value
    if (value && !value.range && value.rangeFn) {
      value.range = value.rangeFn();
    }

    this.previousSelectedOption = value;
    super.writeValue(value);
  }

// Better do ✅
if (value && !value.range && value.rangeFn) {
  value.range = value.rangeFn();
}
```

```js
// Even better on TS
private formChanged(value:object): boolean {
  let reason= {};

  var test1 = () => {
      return this.template.dirty;
  };
  var test2 = () => {
      return this.template.touched;
  };
  var test3 = () => {
      return this.template.value.templateName.length <= 5
  };
  return (test1() ||  test2() || test3() );
}
```

> Functions are first class objects in JavaScript and this allows us to pass them as parameters to other functions.

```js
// insteof of
var calculator = {
  run: function (op, n1, n2) {
    var result;
    if (op === "add") {
      result = n1 + n2;
    } else if (op === "sub") {
      result = n1 - n2;
    } else if (op === "mult") {
      result = n1 * n2;
    } else if (op === "div") {
      result = n1 / n2;
    }
    return result;
  },
};
calculator.run("sub", 5, 3); // 2

// better do
var calculator = {
  add: function (a, b) {
    return a + b;
  },
  sub: function (a, b) {
    return a - b;
  },
  mult: function (a, b) {
    return a * b;
  },
  div: function (a, b) {
    return a / b;
  },
  run: function (fn, a, b) {
    return fn && fn(a, b);
  },
};
calculator.run(calculator.sub, 5, 3); // 2
```

```js
// better ifs
const weekendOrWeekday = (inputDate) => {
  const day = inputDate.getDay();
  if (day === 0 || day === 6) {
    return "weekend";
  }

  return "weekday";
  // Or, for ternary fans:
  // return (day === 0 || day === 6) ? 'weekend' : 'weekday';
};
console.log(weekendOrWeekday(new Date()));

// better do
const weekendOrWeekday = (inputDate) => {
  const day = inputDate.getDay();
  return weekendOrWeekday.labels[day] || weekendOrWeekday.labels["default"];
};
weekendOrWeekday.labels = {
  0: "weekend",
  6: "weekend",
  default: "weekday",
};
console.log(weekendOrWeekday(new Date()));
```

---

## If return the if inlining

```js
function isNumeric(n) {
  return (
    n >= 48 && n <= 57 // inlining using ()
  );
}

isNumeric(53); // true
```

---

## no ifs

```js
function hasValidAppliesTo(location) {
  var locationTest = {
    uk: function () {
      return "uk";
    },
    germany: function () {
      return "germany";
    },
    spain: function () {
      return "spain";
    },
    default: function () {
      return "Default country";
    },
  };
  return (locationTest[location] || locationTest["default"])();
}
hasValidAppliesTo("spain");
```

---

## ifs using Function Delegation

```js
// ❌ instead of 💩
function itemDropped(item, location) {
    if (!item) {
        return false;
    } else if (outOfBounds(location) {
        var error = outOfBounds;
        server.notify(item, error);
        items.resetAll();
        return false;
    } else {
        animateCanvas();
        server.notify(item, location);
    }
}

// better do
// function delegation
function itemDropped(item, location) {
  const dropOut = function () {
    server.notify(item, outOfBounds);
    items.resetAll();
    return false;
  };

  const dropIn = function () {
    server.notify(item, location);
    animateCanvas();
    return true;
  };

  return !!item && (outOfBounds(location) ? dropOut() : dropIn());
}
```

```js
// even better 
// function delegation using typescript
private formChanged(value:object): boolean {
    let reason= {};

    var test1 = () => {
        return this.template.dirty;
    };

    var test2 = () => {
        return this.template.touched;
    };

    var test3 = () => {
        return this.template.value.templateName.length <= 5
    };

    return (test1() ||  test2() || test3() );
}
```

---

## ES6 Rest operators

```js
// ❌ instead of 💩
const newObj = {
  atr1: 1,
  atr2: 2,
};
if (1 === 1) {
  newObj["atr3"] = 3;
}
console.log(newObj);

// Better do ✅
betterDo = (condition, object) => (condition ? object : {});
newObject = {
  atr1: 1,
  atr2: 2,
  ...betterDo(1 === 1, { atr3: 3 }),
}
```

---

## if else if else

```js
// instead of
if (type === "aligator") {
  aligatorBehavior();
} else if (type === "parrot") {
  parrotBehavior();
} else if (type === "dolphin") {
  dolphinBehavior();
} else if (type === "bulldog") {
  bulldogBehavior();
} else {
  throw new Error("Invalid animal " + type);
}

// better do
const type = 'aligator';

const types = {
  aligator: console.log('aligatorBehavior')
  parrot: console.log('parrotBehavior'),
  dolphin: console.log('dolphinBehavior'),
  bulldog: console.log('bulldogBehavior')
};
const foo = types.type;

if (!foo) { throw new Error('Invalid animal ' + JSON.stringify( types )); foo()}
```

---

## Ternary operator with return statements: return boolean ? 'foo' : 'bar'

```js
// 1
// ❌ instead of 💩
function saveCustomer(customer) {
  if (isCustomerValid(customer)) {
    database.save(customer);
  } else {
    alert("customer is invalid");
  }
}

// Better do ✅ 
// ternary equivalent
function saveCustomer(customer) {
  isCustomerValid(customer)
    ? database.save(customer)
    : alert("customer is invalid");
}
```

```js
// 2
// ❌ instead of 💩
if ( 'undefined' !== typeof nn['key'] ) {
  var gradeObject.title;
}
if (gradeObject.value === gradeValue) {
  return gradeObject.title;
}

// Better do ✅
return gradeObject.title
  ? "undefined" !== typeof nn["key"]
  : gradeObject.value === gradeValue;
```

---

## ternary operator: replace ifs

```js
// instead of
const i = 0;
if (Math.random() > 0.5) i++;

// better do
const i = Math.random() > 0.5 ? 1 : 0;
```

---

## nested if-else

```js
// instead
function customerValidation(customer) {
  if (!customer.email) {
    return error("email is require");
  } else if (!customer.login) {
    return error("login is required");
  } else if (!customer.name) {
    return error("name is required");
  } else {
    return customer;
  }
}
```

```js
// ES6 style custom formatted ternary magic
const customerValidation = (customer) =>
  !customer.email
    ? error("email is required")
    : !customer.login
    ? error("login is required")
    : !customer.name
    ? error("name is required")
    : customer;
```

---

## 3 ifs on return

```js
// ❌ instead of 💩
if ( 'undefined' !== typeof nn['key'] ) {
  var gradeObject.title;
}
if (gradeObject.value === gradeValue) {
  return gradeObject.title;
}
```

```js
// Better do ✅
return gradeObject.title
  ? "undefined" !== typeof nn["key"]
  : gradeObject.value === gradeValue;
```

## simplify 3 ifs in a row

```js
// ❌ instead of 💩
if (cache.hasError("required")) {
  that.formErrors = that.validationMessages.error.required;
  return;
}
if (cache.hasError("minlength")) {
  that.formErrors = that.validationMessages.error.minlength;
  return;
}
if (cache.hasError("maxlength")) {
  that.formErrors = that.validationMessages.error.maxlength;
}

// Better do ✅ : bottom top bottom top
return (that.formErrors = that.validationMessages.error.required)? cache.hasError('required'):
     (that.formErrors = that.validationMessages.error.minlength)? cache.hasError('minlength'): 
     (that.formErrors = that.validationMessages.error.maxlength)? cache.hasError('maxlength')
```
	
```js
// 2
// instead of
isButtonLoading(button: Button): boolean {
  if (!button.action.type) {
    return false;
  }

  if (this.isLoading) {
    return enumMatch(Action_Type, button.action.type, Action_Type.SUBMIT);
  }

  if (this.isChatLoading) {
    return enumMatch(Action_Type, button.action.type, Action_Type.CHAT);
  }

return false;
}


// better do
isButtonLoading2(button: Button): boolean {
  return (false) ? !button.action.type:
      (enumMatch(Action_Type, button.action.type, Action_Type.SUBMIT)) ? this.isLoading:
          (enumMatch(Action_Type, button.action.type, Action_Type.CHAT)) ? this.isChatLoading
}
```

---

## execute only this IF

```js
function doIf(condition, func) {
  if (condition) {
    func();
  }
}

// conditional here
const x = "Bananas";

doIf(x === 1, () => {
  console.log("x is equal to 1"); // x is equal to 1
});
doIf(x === "Bananas", () => {
  console.log("x is equal to Bananas");
});
doIf(x < 10 && x > 0, () => {
  console.log("x is between 0 and 10"); // x is between 0 and 10
});

x; // Bananas
```

---

### If using && on return

```js
// ❌ instead of 💩
if (condition) {
  dosomething();
}

// Better do ✅
condition && dosomething()
```

---

## if shorthand notation

```js
// ❌ instead of 💩
if (cache.hasError("required")) {
  that.formErrors = that.validationMessages.error.required;
  return;
}
if (cache.hasError("minlength")) {
  that.formErrors = that.validationMessages.error.minlength;
  return;
}
if (cache.hasError("maxlength")) {
  that.formErrors = that.validationMessages.error.maxlength;
}
```

```js
// Better do ✅ 
// : bottom top bottom top
return (that.formErrors = that.validationMessages.error.required)?  cache.hasError('required'):
       (that.formErrors = that.validationMessages.error.minlength)? cache.hasError('minlength'):
       (that.formErrors = that.validationMessages.error.maxlength)? cache.hasError('maxlength');
```

---

## Better ifs, Improving ifs, ifs improvements, Improve nested conditionals

// before
As if/else blocks get bigger and/or nested they get harder to follow.
This tends to encourage you to write a flexible, well organised and even object-oriented code

```js
// ❌ instead of 💩
if (myAge > legalAge) {
  canDrink = true;
} else {
  canDrink = false;
}

// Better do ✅
const canDrink = myAge > legalAge ? true : false;

// even better
const canDrink = myAge > legalAge;
```

---

## Using let and assign same variable on if

```js
// 1
// ❌ instead of 💩
const hour = 14;
let greeting;
if (hour < 18) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}

// Better do ✅
const isDay = (hour) => hour < 18;
const getGreeting = (hour) => (isDay(hour) ? "Good Day" : "Good Evening");
const greeting = getGreeting(hour);
```

---

## if / else if / else

```js
// ❌ instead of 💩
const fn = (temp) => {
  if (temp === 0) return "water freezes at 0°C";
  else if (temp === 100) return "water boils at 100°C";
  else return `nothing special happens at ${temp}°C`;
};

fn(0); // 'water freezes at 0°C'
fn(50); // 'nothing special happens at 50°C'
fn(100); // 'water boils at 100°C'
```

```js
// Better do ✅
import cond from "mojiscript/logic/cond";
import $ from "mojiscript/string/template";

const fn = cond([
  [0, "water freezes at 0°C"],
  [100, "water boils at 100°C"],
  [() => true, $`nothing special happens at ${0}°C`],
]);

fn(0); //  'water freezes at 0°C'
fn(50); //  'nothing special happens at 50°C'
fn(100); //  'water boils at 100°C'
```

---

## Avoid Longhand

```js
// Longhand
var big;
if (x > 10) {
  big = true;
} else {
  big = false;
}
```

```js
// instead use: Shorthand
var big = x > 10 ? true : false;
```

```js
//even better
var x = 1;
var big = x > 10; //false
```

```js
//even better another example:
var x = 3,
  big = x > 10 ? "greater 10" : x < 5 ? "less 5" : "between 5 and 10";
console.log(big); //"less 5"
```

---

## !== null || !== undefined || !== ''

```js
// ❌ instead of 💩
if (variable1 !== null || variable1 !== undefined || variable1 !== "") {
  var variable2 = variable1;
}
```

```js
// Better do ✅
var variable2 = variable1 || "";
```

---

## true validation

```js
// validate true
if (likeJavaScript === true) {
}
```

```js
//same as
if (likeJavaScript) {
}
```

---

## if true validation - arrow function

```js
// longhand
var a;
if (a != true) {
  // do something...
}
```

```js
// shorthand
var a;
if (!a) {
  // do something...
}
```

```js
// validate true
if (likeJavaScript == true) {
  //    
}
```

```js
//same as
if (likeJavaScript) {
  //
}
```

---

## The simple true/false return

```js
// ❌ instead of 💩
if (condition) {
  return true;
} else {
  return false;
}
```

```js
// better use:
return condition;
```

---

## using multi-action nested ternaries

> Using no error Object literal validation using multi-action nested ternaries

```js
var obj = {};
//obj.foo = {"key":"value"}
//obj.foo.foo2 = {"key2":"value2"}

typeof obj === "undefined"
  ? false
  : typeof obj.foo === "undefined"
  ? false
  : typeof obj.foo.foo2 !== "undefined"
  ? console.log(true + "-" + Object.keys(obj.foo.foo2))
  : false;
```

---

## using ternary conditional

```js
// ❌ instead of 💩
if (isArthur) {
  weapon = "Excalibur";
} else {
  weapon = "katana";
}

// better do
var weapon = isArthur ? "Excalibur" : "Longsword";
```

---

## using ternary conditional returning functions

```js
// ❌ instead of 💩
if (val) {
  return foo();
} else {
  return bar();
}

// Better do ✅
return val ? foo() : bar();
```

—--

## if it is null or empty

```js
// ❌ instead of 💩
if (y != null && y != "") {
  // ...
}
```

```js
// Better do ✅
if (y) {
  // ...
}
```

—--

## if ternary operator: x3

```js
// ❌ instead of 💩
if (cache.hasError("required")) {
  return this.validationMessages.error.required;
}
if (cache.hasError("minlength")) {
  return this.validationMessages.error.minlength;
}
if (cache.hasError("maxlength")) {
  return this.validationMessages.error.maxlength;
}
```

```js
// Better do ✅
cache.hasError("required")
  ? (function () {
      console.log(that.validationMessages.error.required);
      that.formErrors = that.validationMessages.error.required;
      return;
    })()
  : cache.hasError("minlength")
  ? (function () {
      console.log(that.validationMessages.error.minlength);
      that.formErrors = that.validationMessages.error.minlength;
      return;
    })()
  : cache.hasError("maxlength")
  ? (function () {
      console.log(that.validationMessages.error.maxlength);
      that.formErrors = that.validationMessages.error.maxlength;
      return;
    })()
  : "";
```

---

## CHOOSE FUNCTIONS ON THE FLY: ternary operator

```js
isArthur && isKing ?
  function (){
    alert("Hail Arthur, King of the Britons!");
    console.log("Current weapon: Excalibur");
    console.log('excalibur')
  }(); // call the Function expression
  :
  function (){
    alert("Hail Arthur, King of the Britons!");
    console.log("Current weapon: Excalibur");
    console.log('excalibur')
  }(); // call the Function expression
```

```js
// another example
.isEmpty($cope.myTheme[2])?
  function (){
    resetScheme();
  }()
  :
  function (){
    resetScheme();
    paintScheme(elements);
  }();
```

---

## switch statement with object literals

```js
// ❌ instead of 💩
let fruit = "oranges";

switch (fruit) {
  case "apples":
    console.log("Apples");
    break;
  case "oranges":
    console.log("Oranges");
    break;
} // 'Oranges'

const logFruit = {
  apples: () => console.log("Apples"),
  oranges: () => console.log("Oranges"),
};

logFruit[fruit](); // 'Oranges'
```

```js
// Better do ✅
const switchFn =
  (lookupObject, defaultCase = "_default") =>
  (expression) =>
    (lookupObject[expression] || lookupObject[defaultCase])();

const knownFruit = () => console.log("Known fruit");
const unknownFruit = () => console.log("Unknown fruit");

const logFruit = {
  apples: knownFruit,
  oranges: knownFruit,
  default: unknownFruit,
};

const fruitSwitch = switchFn(logFruit, "default");

fruitSwitch("apples"); // 'Known fruit'
fruitSwitch("pineapples"); // 'Unknown fruit'
```

---

## Another example x3 ifs

```js
// ❌ instead of 💩
function sayHello() {
  console.log("sayHello");
}
function giveSomeNews() {
  console.log("giveSomeNews");
}
function sayBye() {
  console.log("sayBye");
}

// declaring name this test
let name = "patrick";
// var name = "jane";

if (name === "patrick") {
  sayHello();
} else if (name === "jane") {
  giveSomeNews();
} else {
  sayBye();
} // sayHello
```

```js
// Better do ✅ : actions declaration & Method lookup using Command
var greetings = {
  patrick: sayHello,
  john: giveSomeNews,
  jane: sayBye,
};

greetings["patrick"](); // sayHello
```

```js
// View
<h4 sizeClass="XL:h3, MS:h2">{{title}}</h4>

// Component
    get title(): string {
        const title = {
            band: 'What is your Diamond budget?',
            stone: 'Whats more important to you?',
            step3: 'Whats more important to you?'
        };
        return title[this.type];
    }
```

---

## switch statement with object literals. MB

```js
function getSnack(type) {
  var snack;

  function isDrink() {
    return (snack = "Drink");
  }
  function isFood() {
    return (snack = "Food");
  }

  var snacks = {
    coke: isDrink,
    pepsi: isDrink,
    cookies: isFood,
    crisps: isFood,
  };
  return snacks[type]();
}

var snack = getSnack("coke");
console.log(snack); // 'Drink'
```

```js
function getDrink(type) {
  var drink;
  var drinks = {
    coke: function () {
      drink = "Coke";
    },
    pepsi: function () {
      drink = "Pepsi";
    },
    lemonade: function () {
      drink = "Lemonade";
    },
    default: function () {
      drink = "Default item";
    },
  };

  // invoke it
  (drinks[type] || drinks["default"])();

  // return a String with chosen drink
  return "The drink I chose was " + drink;
}

var drink = getDrink("coke");
// The drink I chose was Coke
console.log(drink);
```

```js
coke = function () {
  alert("test");
};

function getDrink(type) {
  var drinks = {
    coke: function () {
      return "Coke";
    },
    pepsi: function () {
      return "Pepsi";
    },
    lemonade: function () {
      return "Lemonade";
    },
    default: function () {
      return "Default item";
    },
  };
  return (drinks[type] || drinks["default"])();
}
getDrink("coke"); // alert coke
```

- LINKS
  https://toddmotto.com/deprecating-the-switch-statement-for-object-literals/

---

## Breaking or continuing loop with FP: from better-ifs to no-ifs

Using `.some()` we get iteration functionally similar to .forEach but with the ability to break through return instead. Also there is `.every()`, which can be used. We have to return the opposite boolean compared to `.some()`

```js
// Using .some to break a loop
const isBiggerThan10 = (numb) => numb > 10;
[2, 5, 8, 1, 4].some(isBiggerThan10); // false
[12, 5, 8, 1, 4].some(isBiggerThan10); // true
```

```js
// Using .every to brack a loop
const isSmallerThan10 = (num) => num < 10;
console.log([2, 5, 8, 1, 4].every(isSmallerThan10)); // true
console.log([12, 5, 8, 1, 4].every(isSmallerThan10)); // false
```

---

## Long if statement: Or's - all ||'s - better ors

1.

```js
// ❌ instead of 💩
myvar = 1;
if (myvar == 1 || myvar == 5 || myvar == 7 || myvar == 22) alert("yeah"); // yeah
```

```js
// better
myvar = 1;
if ([1, 5, 7, 22].indexOf(myvar) !== -1) alert("yeah"); // yeah
```

```js
// even better with ES6
myvar = 1;
if ([1, 5, 7, 22].includes(myvar)) alert("yeah"); // yeah
```

2.

```js
// not good: we validate existance
if (
  toConfirmEnRoute !== undefined &&
  toConfirmEnRoute !== null &&
  toConfirmEnRoute === true
) {
  console.log("IN");
}
```

```js
// better: validate typeof
if (typeof toConfirmEnRoute !== "undefined" && toConfirmEnRoute === true) {
  console.log("IN");
}
```

3.

```js
// ❌ instead of 💩
if (node && node.kids && node.kids[index]) {
  foo(node.kids[index]);
}
```

```js
// Better do ✅
var kid = node && node.kids && node.kids[index];
if (kid) {
  foo(kid);
}
```

4.

```js
// ❌ instead of 💩
if (gradeValue !== undefined && gradeValue !== null && gradeValue.length > 0) {
  console.log("IN");
}
```

```js
// better: validate typeof
if (gradeValue && gradeValue.length > 0) {
  console.log("IN");
}
```

---

### Several ids

```js
// ❌ instead of 💩
function selector(x) {
  if (x === "Jhon") {
    return `Jhonny Depp`;
  }
  if (x === "Dave") {
    return `Dave Grohl`;
  }
  if (x === "Jim") {
    return `Jim Morrison`;
  }
  if (x === "Katty") {
    return `Katty Perry`;
  }
  if (x === "Tom") {
    return `Tom Hardy`;
  }
  return "Dont have this name >(";
}
```

```js
// Better do ✅
// you can input selectorObj from outside if you dont want to create it every time you invoke betterSelector
function betterSelector(x) {
  const selectorObj = {
    Jhon: "Jhonny Depp",
    Dave: "Dave Grohl",
    Jim: "Jim Morrison",
    Katty: "Katty Perry",
    Tom: "Tom Hardy",
  };
  // here you can use ternary if you have complicated logic
  return selectorObj[x] || "Dont have this name >(";
}

console.log(betterSelector("Jhon"));
console.log(betterSelector("qwe"));
console.log(selector("Jhon"));
```

---

### Better returns. If returns improvements

```js
// ❌ instead of 💩
if (a == b) {
  return true;
} else {
  return false;
}
```

```js
// Better do ✅
return a == b;
```

### Implicit Return Shorthand (short return)

Return is a keyword we use often to return the final result of a function. An arrow functions with a single statement will implicitly return the result its evaluation (the function must omit the braces ({}) in order to omit the return keyword).

To return a multi-line statement (such as an object literal), 't's necessary to use () instead of {} to wrap your function body. This ensures the code is evaluated as a single statement.

```js
// instead
function calcCircumference(diameter) {
  return Math.PI * diameter;
}
```

```js
// Better do ✅
calcCircumference = diameter => (
  Math.PI * diameter;
)
```

---

### Improving and removing switch. Favor `Object Literal` than `Switch Statement`

```js
getDescriptions(code: string, filterId: string) {
  switch (filterId) {
      case 'gem_shape': {
          if (code == gemShapeDesc[code].key) return gemShapeDesc[code].description;
          break;
      }
      case 'design_style': {
          switch (code) {
              case 'Side Stone': {
                  this.newCode = code.replace('Side Stone', 'Side_Stone');
                  return designStyleDesc[this.newCode].description;
                  break;
              }
              default: {
                  if (code == designStyleDesc[code].key) return designStyleDesc[code].description;
                  break;
              }
          }
      }
      case 'design_setting': {
          switch (code) {
              case 'Classic Tapered': {
                  this.newCode = code.replace('Classic Tapered', 'Classic_Tapered');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Classic Side Stone': {
                  this.newCode = code.replace('Classic Side Stone', 'Classic_Side_Stone');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Knife Edge': {
                  this.newCode = code.replace('Knife Edge', 'Knife_Edge');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'VASHI Signature': {
                  this.newCode = code.replace('VASHI Signature', 'VASHI_Signature');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Twist Pavé': {
                  this.newCode = code.replace('Twist Pavé', 'Twist_Pavé');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Modern Graduating': {
                  this.newCode = code.replace('Modern Graduating', 'Modern_Graduating');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Four Claw': {
                  this.newCode = code.replace('Four Claw', 'Four_Claw');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Crossover Pavé': {
                  this.newCode = code.replace('Crossover Pavé', 'Crossover_Pavé');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Three-Sided Pavé': {
                  // this.newCode = code.replace('Three-Sided Pavé', 'Three_Sided_Pavé');
                  // console.log('code replace Three_Sided_Pavé is now: ' + this.newCode);
                  return 'Hello world '; // designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Princess Cut': {
                  this.newCode = code.replace('Princess Cut', 'Princess_Cut');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Princess Channel': {
                  this.newCode = code.replace('Princess Channel', 'Princess_Channel');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Channel Set': {
                  this.newCode = code.replace('Channel Set', 'Channel_Set');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'French Cut': {
                  this.newCode = code.replace('French Cut', 'French_Cut');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Two-Sided Pavé': {
                  this.newCode = code.replace('Two-Sided Pavé', 'Two_Sided_Pavé');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'V1 Pavé': {
                  this.newCode = code.replace('V1 Pavé', 'V1_Pavé');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Contour Pavé': {
                  this.newCode = code.replace('Contour Pavé', 'Contour_Pavé');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Simple Halo': {
                  this.newCode = code.replace('Simple Halo', 'Simple_Halo');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Three Stone': {
                  this.newCode = code.replace('Three Stone', 'Three_Stone');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'VASHI Signature Trilogy': {
                  this.newCode = code.replace('VASHI Signature Trilogy', 'VASHI_Signature_Trilogy');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'VASHI Knife Edge': {
                  this.newCode = code.replace('VASHI Knife Edge', 'VASHI_Knife_Edge');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'VASHI Graduating Five Stone': {
                  this.newCode = code.replace('VASHI Graduating Five Stone', 'VASHI_Graduating_Five_Stone');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Rubover Trilogy': {
                  this.newCode = code.replace('Rubover Trilogy', 'Rubover_Trilogy');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Rex Three Stone (Emeralds)': {
                  this.newCode = code.replace('Rex Three Stone (Emeralds)', 'Rex_Three_Stone_Emeralds');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Rex Three Stone (Rubies)': {
                  this.newCode = code.replace('Rex Three Stone (Rubies)', 'Rex_Three_Stone_Rubies');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Rex Three Stone (Sapphires)': {
                  this.newCode = code.replace('Rex Three Stone (Sapphires)', 'Rex_Three_Stone_Sapphires');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Pavé Set (Rubies)': {
                  this.newCode = code.replace('Pavé Set (Rubies)', 'Pavé_Set_Rubies');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Pavé Set (Emeralds)': {
                  this.newCode = code.replace('Pavé Set (Emeralds)', 'Pavé_Set_Emeralds');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              case 'Pavé Set (Sapphires)': {
                  this.newCode = code.replace('Pavé Set (Sapphires)', 'Pavé_Set_Sapphires');
                  return designSettingDesc[this.newCode].description;
                  break;
              }
              default: {
                  if (designSettingDesc[code] === undefined) {
                      return 'Hello World (design_setting)';
                  } else {
                      return designSettingDesc[code].description;
                  }
                  break;
              }
          }
      }
      case 'metal': {
          switch (code) {
              case '18k White Gold': {
                  this.newCode = code.replace('18k White Gold', 'Eighteen_White_Gold');
                  return metalDesc[this.newCode].description;
                  break;
              }
              case '18k Yellow Gold': {
                  this.newCode = code.replace('18k Yellow Gold', 'Eighteen_Yellow_Gold');
                  return metalDesc[this.newCode].description;
                  break;
              }
              case '18k Rose Gold': {
                  this.newCode = code.replace('18k Rose Gold', 'Eighteen_Rose_Gold');
                  return metalDesc[this.newCode].description;
                  break;
              }
              default: {
                  if (code == metalDesc[code].key) return metalDesc[code].description;
                  break;
              }
          }
      }
      default: {
          break;
      }
  }
}
```

```js
// Better do ✅ : Favor `Object Literal` than `Switch Statement`
designStyleReplace = (code: string) => {
    const codeReplaced = code.replace(/\s/g, '_')
    return (typeof designStyleDesc[codeReplaced] !== 'undefined')? designStyleDesc[codeReplaced].description: ''
}
designSettingReplace = (code: string) => {
    const codeReplaced = code.replace('(', '_').replace(')', '_').replace(/\s/g, '_')
    return (typeof designSettingDesc[codeReplaced] !== 'undefined')? designSettingDesc[codeReplaced].description: ''
}
designMetalReplace = (code: string) => {
    const codeReplaced = code.replace('18k', 'Eighteen').replace(/\s/g, '_')
    return (typeof metalDesc[codeReplaced] !== 'undefined')? metalDesc[codeReplaced].description: ''
}

gemShape = (code: string) => {
    return (typeof gemShapeDesc !== 'undefined' && typeof gemShapeDesc[code] !== 'undefined' && code === gemShapeDesc[code].key)?  gemShapeDesc[code].description: undefined
}

designStyleDefault = (code: string) => {
    return (typeof designStyleDesc !== 'undefined' && typeof designStyleDesc[code] !== 'undefined' && code === designStyleDesc[code].key)? designStyleDesc[code].description: undefined
}
designStyle = (code) => {
    const gemTestCode = {
        'Side Stone':  this.designStyleReplace(code)
    }
    return gemTestCode[code] || this.designStyleDefault(code);
}

designSettingDefault = (code) => {
    return (designSettingDesc[code] !== undefined)? designSettingDesc[code].description : 'WIP: (design_setting)'
}
designSetting = (code) => {
    const gemTestCode = {
        'Classic Tapered':  this.designSettingReplace(code),
        'Classic Side Stone':  this.designSettingReplace(code),
        'Knife Edge':  this.designSettingReplace(code),
        'Twist Pavé':  this.designSettingReplace(code),
        'Modern Graduating':  this.designSettingReplace(code),
        'Four Claw':  this.designSettingReplace(code),
        'Crossover Pavé':  this.designSettingReplace(code),
        'Three-Sided Pavé':  'WIP: Three-Sided Pavé',
        'Princess Channel':  this.designSettingReplace(code),
        'Channel Set':  this.designSettingReplace(code),
        'French Cut':  this.designSettingReplace(code),
        'Two-Sided Pavé':  this.designSettingReplace(code),
        'V1 Pavé':  this.designSettingReplace(code),
        'Contour Pavé':  this.designSettingReplace(code),
        'Simple Halo':  this.designSettingReplace(code),
        'Three Stone':  this.designSettingReplace(code),
        'VASHI Signature':  this.designSettingReplace(code),
        'VASHI Signature Trilogy':  this.designSettingReplace(code),
        'VASHI Knife Edge': this.designSettingReplace(code),
        'VASHI Graduating Five Stone':  this.designSettingReplace(code),
        'Rubover Trilogy':  this.designSettingReplace(code),
        'Rex Three Stone (Emeralds)':  this.designSettingReplace(code),
        'Rex Three Stone (Rubies)':  this.designSettingReplace(code),
        'Rex Three Stone (Sapphires)':  this.designSettingReplace(code),
        'Pavé Set (Rubies)':  this.designSettingReplace(code),
        'Pavé Set (Emeralds)':  this.designSettingReplace(code),
        'Pavé Set (Sapphires)':  this.designSettingReplace(code)
    }
    return gemTestCode[code] || this.designSettingDefault(code)
}

designMetalDefault = (code) => {
    return (metalDesc[code] !== undefined)? metalDesc[code].description: 'WIP: (design_setting)'
}
designMetal = (code) => {
    const gemTestCode = {
        '18k White Gold':  this.designMetalReplace(code),
        '18k Yellow Gold':  this.designMetalReplace(code),
        '18k Rose Gold':  this.designMetalReplace(code)
    }
    return gemTestCode[code] || this.designMetalDefault(code);
}

/**
* Retrieves descriptions for product elements based on their respected code
*/
getDescriptions(code: string, filterId: string) {
    const gemFilterID = {
        'gem_shape':  this.gemShape(code),
        'design_style':  this.designStyle(code),
        'design_setting':  this.designSetting(code),
        'metal':  this.designMetal(code)
    }
    return gemFilterID[filterId] || [];
}
```

---

### Default Parameter Values. 2x ifs. return with undefined validation

You can use the if statement to define default values for function parameters. In ES6, you can define the default values in the function declaration itself.

```js
// ej1
// ❌ instead of 💩
function foo(x, y, z) {
  if (y === undefined) y = 7;
  if (z === undefined) z = 42;
  return x + y + z;
}
```

```js
// Better do ✅
function foo(x, y = 7, z = 42) {
  return x + y + z;
}
```

```js
// ej2
function volume(l, w, h) {
  if (w === undefined) w = 3;
  if (h === undefined) h = 4;
  return l * w * h;
}
```

```js
volume = (l, w = 3, h = 4) => l * w * h;
volume(2); // 24
```

---

### Non-branching strategies: Property look-ups. utility

```js
// ❌ instead of 💩 
// namespace chaining looking
fileManager.toolbar.clicked = function (buttonId) {
  switch (buttonId) {
    case "open":
      fileManager.openNew(true);
      break;
    case "save":
      fileManager.saveSelected(true);
      break;
    case "run":
      fileManager.executeSelected(true);
      break;
    default:
      coreUtils.notImplemented();
  }
};
fileManager.toolbar.clicked("save");
```

```js
// better: hash table for lookup, make a generic function
fileManager.toolbarActions = {
  open: { fn: fileManager.openNew, args: [true] },
  save: { fn: fileManager.saveSelected, args: [false] },
  run: { fn: fileManager.execSelected, args: [false] },
  default: { fn: coreUtils.notImplemented, ctxt: coreUtils },
};

toolbar.clicked = function (actions, buttonId) {
  var action = actions[buttonId] || actions["default"];
  action.fn.apply(action.ctxt, action.args);
};

toolbar.clicked(fileManager.toolbarActions, "save");
```

---

### 3 values 2 ifs

```js
// es5
function foo(x, y, z) {
  if (y === undefined) {
    y = 7;
  }
  if (z === undefined) {
    z = 42;
  }
  return x + y + z;
}
```

```js
// better es6
function foo(x, y = 7, z = 42) {
  return x + y + z;
}
```

---
