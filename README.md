# JavaScript `❌ instead of 💩` -> `Better do ✅`

## Compendium of JavaScript Script Practices for Implementing JavaScript Best Practices

This document serves as a comprehensive collection of JavaScript code snippets and techniques designed to promote and implement best practices. It aims to guide developers away from common pitfalls and inefficient patterns, encouraging the adoption of cleaner, more concise, and robust solutions. Each section presents a "bad practice" example (marked with `❌ instead of 💩`) alongside its improved counterpart (marked with `Better do ✅`), highlighting the benefits of the recommended approach.

## This compendium covers a wide range of topics, including:

* **Falsy-checks:** Efficiently evaluating the falsiness of values.
* **Ternary-operators:** Writing concise conditional expressions.
* **Return-after-comparison:** Simplifying conditional return statements.
* **Default-parameter-values:** Setting default function parameters.
* **Console-logging:** Shortening and improving console logging practices.
* **Function-arguments:** Using objects for function arguments instead of long argument lists.
* **Arguments-object:** Understanding and replacing the deprecated `arguments` object.
* **Implicit-returns:** Utilizing arrow function expressions for implicit returns.
* **Deep-object-array-access:** Safely retrieving values from nested structures.
* **Clamping:** Ensuring values stay within a specified range.
* **Grouping-and-collecting-data:** Using `groupBy` and `collectBy` for data organization.
* **Flattening-arrays:** Creating flat arrays from nested structures.
* **Indexing-arrays:** Indexing array elements using `indexBy`.
* **Difference-between-arrays-of-objects:** using keying function to find differences.
* **URL-validation:** Validating URLs.
* **Array-creation:** Generating arrays of numbers.
* **Object-mapping:** Transforming object keys and values.
* **Credit-card-validation:** Validating credit card numbers.
* **Sorting:** Implementing ascending comparators.
* **Object-declaration:** Properly declaring empty objects.
* **ES6-default-parameters:** Using default parameters in functions.
* **Template-string-replacement:** Implementing simple template string replacement.
* **DOM-debugging:** Debugging DOM elements with visual aids.
* **Array-member-counting:** Counting the occurrences of array elements.
* **Filtering-empty-values:** Removing empty values from arrays.
* **Array-merging:** Merging arrays immutably.
* **Object-and-array-modification:** Modifying objects and arrays immutably using the spread operator.
* **Conditional-execution:** Executing code based on object or array emptiness.
* **URL-parameter-removal:** Removing URL parameters.
* **URLSearchParams:** Working with URL query parameters.
* **Cookie-handling:** Clearing and retrieving cookie values.
* **Text-selection:** Getting selected text.
* **Page-scrolling:** Scrolling to the top of the page.
* **Date-interval-calculation:** Calculating the interval between two dates.
* **Tab-visibility:** Determining if the current tab is active.
* **Array-emptiness-check:** Checking if an array is empty.
* **Random-ID-generation:** Generating random IDs.
* **Star-ratings:** Generating star ratings.
* **Object-emptiness-validation:** validating if an object is empty.
* **Search-and-parse-object-properties:** Searching for and parsing object properties.
* **String-manipulation:** Removing trailing slashes and decapitalizing strings.
* **Random-number-generation:** Generating random number strings and integers.
* **Boolean-toggling:** Toggling boolean values.
* **NodeList-conversion:** Converting NodeLists to arrays.
* **String-slugification:** Converting strings to slugs.
* **String-capitalization:** Capitalizing strings.
* **Array-emptiness-check:** Checking if an array is empty.
* **Object-emptiness-check:** Checking if an object is empty.
* **Random-integer-generation:** Generating random integers within a range.
* **Random-boolean-generation:** Generating random boolean values.
* **Asynchronous-waiting:** Implementing asynchronous waiting/sleeping.
* **Weekday-determination:** Determining if a date is a weekday.
* **String-reversal:** Reversing strings and arrays of strings.
* **Even-odd-number-checks:** Checking if a number is even or odd.
* **Array-element-counting:** Counting the occurrences of array elements.
* **Array-value-searching:** Searching for values within arrays.
* **Nested-array-emptiness-checks:** Checking for emptiness in nested arrays.
* **Optional-chaining:** Utilizing optional chaining for safe property access.
* **Declarative-coding:** Writing more declarative code.
* **Callback-hell-removal:** Avoiding callback hell with async/await.
* **Function-parameter-reduction:** Reducing function parameters.
* **Array-value-operations:** Operating on array values.
* **Immutable-object-modification:** Modifying objects immutably.
* **Template-literal-types:** Using template literal types in TypeScript.
* **Object-property-validation:** Validating the existence of object properties.
* **Range-printing:** Printing ranges natively in JavaScript.
* **Object-property-checking:** Checking for property existence in objects.
* **Conditional-property-insertion:** Conditionally inserting properties into objects.
* **Duplicate-finding:** Finding duplicates in arrays.
* **Shallow-comparison:** Performing shallow object comparisons.
* **Latest-array-value-retrieval:** Retrieving the latest value from an array.
* **Array-difference:** finding the difference between 2 arrays.
* **Whitespace-detection:** Detecting whitespace in strings.
* **for-of-and-for-in-loops:** Understanding and using `for...of` and `for...in` loops.
* **Event-handling-comparison:** Comparing event handling with JS and RxJS.

---
### :100: <i>Thanks!</i>
#### Now, don't be an stranger. Let's stay in touch!

<a href="https://github.com/leolanese" target="_blank" rel="noopener noreferrer">
  <img src="https://scastiel.dev/api/image/leolanese?dark&removeLink" alt="leolanese’s GitHub image" width="600" height="314" />
</a>

##### :radio_button: gitroll: <a href="https://gitroll.io/profile/uCOZ9SM8b7ne9h17NuPuKVky9uFh2" target="_blank">LeoLanese</a>
##### :radio_button: Linkedin: <a href="https://www.linkedin.com/in/leolanese/" target="_blank">LeoLanese</a>
##### :radio_button: Twitter: <a href="https://twitter.com/LeoLanese" target="_blank">@LeoLanese</a>
##### :radio_button: DEV.to: <a href="https://www.dev.to/leolanese" target="_blank">dev.to/leolanese</a>
##### :radio_button: Blog: <a href="https://www.leolanese.com/blog" target="_blank">leolanese.com/blog</a>
##### :radio_button: Questions / Suggestions / Recommendations: `developer@leol
