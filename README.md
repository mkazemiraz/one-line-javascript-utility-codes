# One-line JavaScript Utility Codes

![One-line JavaScript Utility Codes](./assets/cover.png)

[![Open Source Helpers](https://www.codetriage.com/mkazemiraz/one-line-javascript-utility-codes/badges/users.svg)](https://www.codetriage.com/mkazemiraz/one-line-javascript-utility-codes)

If you like this content, you can ping me or follow me on Twitter 👊

[![Twitter URL](https://img.shields.io/twitter/url?url=https%3A%2F%2Ftwitter.com%2Fmkazemiraz&style=social&logo=twitter&label=Follow%20%40mkazemiraz)](https://twitter.com/mkazemiraz)

## Introduction

😍 Welcome to the One-Line JavaScript Utility Codes repository! Here, we aim to provide you with a curated collection of powerful and concise JavaScript utility functions that can be written in just one line of code.

### Motivation

In the world of software development, efficiency and productivity are crucial factors for success. As developers, we often find ourselves performing repetitive tasks or writing lengthy code to accomplish simple operations. This is where one-line utility codes come to the rescue!

The primary motivation behind this repository is to empower developers like you with a toolbox of concise and reusable utility functions that can significantly simplify your code and boost your productivity. With these one-liners, you'll be able to accomplish common tasks quickly and elegantly, saving you valuable time and effort.

By leveraging the expressive nature of JavaScript, we have carefully crafted these utility functions to encapsulate complex logic into a single line, without sacrificing readability or performance. Each utility code is designed to be self-contained, meaning you can easily copy and paste it into your projects without any dependencies.

Whether you're a beginner learning JavaScript or an experienced developer seeking to optimize your workflow, this repository has something for everyone. We cover a wide range of use cases, including string manipulation, array operations, mathematical calculations, date and time handling, object manipulation, and much more.

Furthermore, we encourage collaboration and community participation. If you have your own powerful one-liners that you'd like to share with the world, we invite you to contribute to this repository. Together, we can build a comprehensive library of JavaScript utility codes that will benefit developers worldwide.

So go ahead, explore the repository, and unlock the potential of these one-line utility codes. Simplify your code, increase your productivity, and take your JavaScript skills to the next level. Let's make coding simpler, one line at a time! 🤟

## Table of Contents

- [Copy text to clipboard](#copy-text-to-clipboard)
- [Shuffle an array](#shuffle-an-array)
- [Convert rgba color code to hexadecimal](#convert-rgba-color-code-to-hexadecimal)
- [Convert hexadecimal color code to rgb](#convert-hexadecimal-color-code-to-rgb)
- [Calculates the average value of a list of number](#calculates-the-average-value-of-a-list-of-number)
- [Check a number is even or odd](#check-a-number-is-even-or-odd)
- [Remove duplicate elements from array](#remove-duplicate-elements-from-array)
- [Check an object is empty](#check-an-object-is-empty)
- [Reverse a string](#reverse-a-string)
- [Calculate the number of days between two dates](#calculate-the-number-of-days-between-two-dates)
- [Capitalize text](#capitalize-text)
- [Generate a random string](#generate-a-random-string)
- [Generate a random number between two numbers](#generate-a-random-number-between-two-numbers)
- [Clear all cookies](#clear-all-cookies)
- [Scroll to top](#scroll-to-top)
- [Generate a random boolean](#generate-a-random-boolean)
- [Identify the type of a data](#identify-the-type-of-a-data)
- [Calculate percent]("#calculate-percent)
- [Get a random item of array](#get-a-random-item-of-array)
- [Sort array of objects based on the values of the specified key](#sort-array-of-objects-based-on-the-values-of-the-specified-key)
- [Check if arrays / objects are equal](#check-if-arrays--objects-are-equal)
- [Add a new item to the array at the specified position](#add-a-new-item-to-the-array-at-the-specified-position)
- [Add commas to number](#add-commas-to-number)

### Copy text to clipboard

```javascript
const copyToClipboard = text => addEventListener('click', _ => navigator.clipboard.writeText(text).catch(console.warn), {once: true});
```

#### Code Explanation

The code snippet provided defines a JavaScript function called `copyToClipboard` that takes a text parameter. The purpose of this function is to copy the specified `text` to the user's clipboard.

The function utilizes the `navigator.clipboard.writeText()` method, which is a built-in browser API for writing text to the clipboard. This method takes the `text` parameter as input and attempts to write it to the clipboard and returns a `Promise`. We chain `Promise.protoype.catch()` to handle errors or exceptions.

Asynchronous `clipboard` write and read requires the calling `document` to be focused (user activation). `addEventListener('click', handler, {once: true})` is used to copy text to the clipboard when the `window` of the calling `document` is clicked after the function is called. 
#### Usage

```javascript
copyToClipboard("Hello, Mkazemiraz!");
```

> Note that this function relies on the availability of the `navigator.clipboard` API, which is supported by most modern browsers. If the API is not available in the user's browser, this code may not function as intended, and appropriate fallback mechanisms should be considered.

### Shuffle an array

```javascript
const shuffleArray = (array) => array.sort(() => Math.random() - 0.5);
```

#### Code Explanation

The provided code defines a JavaScript function called `shuffleArray` that takes an array (`array`) as a parameter. The purpose of this function is to shuffle the elements of the array randomly.

The `sort` method is applied to the `array`, and a comparator function is passed as an argument. The comparator function uses `Math.random()` to generate a random number between 0 and 1. By subtracting 0.5 from this random number, the comparator function returns a positive or negative value, randomly changing the order of the array elements during the sorting process.

By leveraging the built-in `sort` method with a random comparator, this one-liner provides a concise way to shuffle an array in JavaScript.

#### Usage

```javascript
const myArray = [1, 2, 3, 4, 5];
shuffleArray(myArray);
console.log(myArray); // Outputs a randomly shuffled version of the array
```

> Please note that this shuffling technique is not guaranteed to produce perfectly uniform or unbiased results, especially for large arrays. For more rigorous shuffling requirements, you may need to explore alternative algorithms or libraries.

### Convert rgba color code to hexadecimal

```javascript
const rgbToHex = (r, g, b) =>
  "#" + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1);
```

#### Code Explanation

This code defines a function `rgbToHex` that takes three parameters (`r`, `g`, and `b`) representing the red, green, and blue components of an RGB color code, respectively. It converts the RGB color code to its corresponding hexadecimal representation.

The code works by performing bitwise operations and string manipulation to convert the RGB components to hexadecimal values. Here's how it works:

1. The expression `(1 << 24) + (r << 16) + (g << 8) + b` combines the RGB components into a single integer value. Bitwise shift operators (`<<`) are used to position each component at the appropriate bit position: red at 16 bits, green at 8 bits, and blue at 0 bits. The `<< 24` is used to ensure that the highest 8 bits are set to 1, as a placeholder for the alpha component (not included in this code).

2. The resulting integer value is converted to a hexadecimal string using `.toString(16)`. The `16` parameter specifies the radix for the conversion, which represents the base of the numeral system (in this case, hexadecimal).

3. The `.slice(1)` method is applied to remove the leading "1" from the hexadecimal string. This is necessary because the bitwise operation (`1 << 24`) sets the highest bit to 1, which adds an extra digit in the hexadecimal representation.

4. Finally, the "#" symbol is concatenated with the resulting hexadecimal string to form the complete hexadecimal color representation.

#### Usage

```javascript
const hexColor = rgbToHex(255, 0, 128);
console.log(hexColor); // Outputs "#ff0080"
```

> Please note that this code assumes valid input values for the RGB components (`r`, `g`, and `b`) within the range of 0 to 255. If you have different requirements or need to handle edge cases, you may need to modify the code accordingly.

### Convert hexadecimal color code to rgb

```javascript
const hexToRgba = (hex) => {
  const [r, g, b] = hex.match(/\w\w/g).map((val) => parseInt(val, 16));
  return `rgba(${r}, ${g}, ${b})`;
};
```

#### Code Explanation

This code defines a function `hexToRgba` that takes a hexadecimal color code as a parameter (`hex`). It converts the hexadecimal color code to its corresponding RGBA representation.

Here's a breakdown of how the code works:

1. The code uses the `match` method on the `hex` string to extract pairs of two characters (`/\w\w/g`). Each pair represents the red, green, and blue components of the color in hexadecimal format.

2. The `map` method is then applied to the extracted pairs of characters. Within the `map` callback function, `parseInt(val, 16)` is used to convert each pair of characters from hexadecimal to decimal.

3. The resulting decimal values for the red, green, and blue components are destructured into the variables `r`, `g`, and `b`, respectively.

4. Finally, the function returns a string representing the RGBA color value using the interpolated values of `r`, `g`, and `b`.

#### Usage

```javascript
const hexColor = "#ff0080";
const rgbaColor = hexToRgba(hexColor);
console.log(rgbaColor); // Outputs "rgba(255, 0, 128)"
```

### Calculates the average value of a list of number

```javascript
const average = (...args) => args.reduce((a, b) => a + b, 0) / args.length;
```

#### Code Explanation

This code defines a function `average` that calculates the average value of a list of numbers. The function takes any number of arguments using the rest parameter syntax (`...args`), allowing you to pass in a variable number of arguments.

Here's a breakdown of how the code works:

1. The `reduce` method is called on the `args` array, starting with an initial value of `0`. This method iterates over each element in the array and accumulates the sum of all the elements.

2. The callback function `(a, b) => a + b` is used in the `reduce` method. It takes two parameters `a` and `b`, representing the accumulated value and the current element, respectively. The sum of `a` and `b` is computed for each iteration.

3. After the `reduce` operation completes, the sum of all the elements in `args` is divided by the length of the `args` array using the `/` operator. This calculates the average value.

4. The computed average value is then returned by the `average` function.

#### Usage

```javascript
const result = average(4, 8, 12, 16);
console.log(result); // Outputs 10
```

> The code provides a concise way to calculate the average of a set of numbers, making it convenient for scenarios where you need to compute the average dynamically with varying numbers of input values.

### Check a number is even or odd

```javascript
const isOdd = (num) => num % 2 !== 0;
```

#### Code Explanation

This code defines a function `isOdd` that takes a number (`num`) as a parameter. It determines whether the given number is odd or not by performing a simple check.

Here's an explanation of how the code works:

1. The code uses the modulo operator (`%`) to divide the `num` by `2`. The modulo operation calculates the remainder when `num` is divided by `2`.

2. The result of the modulo operation is compared to `0` using the strict inequality operator (`!==`). If the result is not equal to `0`, it means that the number is odd because odd numbers leave a remainder of `1` when divided by `2`.

3. The function returns a boolean value (`true` or `false`) based on the result of the comparison. If the number is odd, the expression `num % 2 !== 0` evaluates to `true`, indicating that the number is odd. Otherwise, if the number is even, the expression evaluates to `false`.

#### Usage

```javascript
console.log(isOdd(5)); // Outputs true
console.log(isOdd(10)); // Outputs false
```

### Remove duplicate elements from array

```javascript
const uniqueArray = (arr) => [...new Set(arr)];
```

#### Code Explanation

This code defines a function `uniqueArray` that takes an array (`arr`) as a parameter. It returns a new array that contains only the unique elements from the input array, removing any duplicate values.

Here's an explanation of how the code works:

1. The code uses the `Set` object to create a new set `new Set(arr)` from the input array. The `Set` object only allows unique values, automatically eliminating any duplicate elements.

2. The spread syntax (`...`) is used to convert the set back into an array. By spreading the elements of the set within a new array `[...new Set(arr)]`, a new array is created with only the unique elements.

3. The resulting array, containing only the unique elements from the input array, is then returned by the `uniqueArray` function.

#### Usage

```javascript
const numbers = [1, 2, 3, 4, 4, 3, 2, 1];
const uniqueNumbers = uniqueArray(numbers);
console.log(uniqueNumbers); // Outputs [1, 2, 3, 4]
```

### Check an object is empty

```javascript
const isEmptyObject = (obj) => obj && Object.keys(obj).length === 0;
```

#### Code Explanation

This code defines a function `isEmptyObject` that takes an object (`obj`) as a parameter. It checks if the object is empty by using two conditions.

Here's an explanation of how the code works:

1. The `obj &&` condition checks if the object `obj` is truthy (not null or undefined). If `obj` is falsy, the condition short-circuits, and the function immediately returns `false`, indicating that the object is not empty.

2. The `Object.keys(obj).length === 0` condition checks if the number of own properties in the object is equal to `0`. `Object.keys(obj)` retrieves an array of all the enumerable own property names of the object, and `length === 0` checks if this array is empty. If the object has no own properties, this condition evaluates to `true`.

The combination of these two conditions ensures that the function returns `true` only if the object is both truthy and has no own properties, indicating that it is empty. If any of the conditions is not met, the function returns `false`, indicating that the object is not empty.

#### Usage

```javascript
const emptyObj = {};
const nonEmptyObj = { key: "value" };
const nullObj = null;

console.log(isEmptyObject(emptyObj)); // Outputs true
console.log(isEmptyObject(nonEmptyObj)); // Outputs false
console.log(isEmptyObject(nullObj)); // Outputs false
```

### Reverse a string

```javascript
const reverseStr = (str) => (str ?? "").split("").reverse().join("");
```

#### Code Explanation

This code defines a function called `reverseStr` that takes a string `str` as a parameter. It performs the following operations to reverse the string:

1. `str.split('')` splits the string into an array of individual characters. Each character becomes an element of the array.

2. `.reverse()` reverses the order of elements in the array, effectively reversing the order of characters in the string.

3. `.join('')` joins the elements of the array back into a string, with no separator between them. This results in the reversed string.

#### Usage

```javascript
console.log(reverseStr("Hello")); // Outputs 'olleH'
```

### Calculate the number of days between two dates

```javascript
const dayDiff = (d1, d2) =>
  Math.ceil(Math.abs(d1.getTime() - d2.getTime()) / 86400000);
```

#### Code Explanation

This code defines a function called `dayDiff` that calculates the number of days between two given dates (`d1` and `d2`).

Here's a breakdown of how the code works:

1. `d1.getTime()` and `d2.getTime()` retrieve the numeric representation of the given dates in milliseconds since January 1, 1970 (Unix timestamp).

2. `Math.abs(d1.getTime() - d2.getTime())` calculates the absolute difference between the two timestamps, representing the duration in milliseconds.

3. The result of the difference is divided by `86400000`, which is the number of milliseconds in a day, to convert the duration from milliseconds to days.

4. `Math.ceil()` rounds up the calculated number of days to the nearest whole number, ensuring that partial days are rounded up.

5. The final result is returned by the arrow function.

#### Usage

```javascript
const date1 = new Date("2023-07-01");
const date2 = new Date("2023-07-05");

console.log(dayDiff(date1, date2)); // Outputs 4
```

> Please note that this code assumes valid input values for `dayDiff` function. It may throw errors or unexpected results if invalid inputs are provided.

### Capitalize Text

```javascript
const capitalize = (str) => str.charAt(0).toUpperCase() + str.slice(1);
```

#### Code Explanation

This code defines a function called `capitalize` that capitalizes the first character of a given string `str`.

Here's a breakdown of how the code works:

1. `str.charAt(0)` retrieves the first character of the string `str`.

2. `.toUpperCase()` converts the first character to uppercase.

3. `str.slice(1)` extracts the remaining characters of the string starting from the second character.

4. The capitalized first character and the remaining characters are concatenated using the `+` operator.

5. The final result is returned by the arrow function.

#### Usage

```javascript
console.log(capitalize("hello")); // Outputs 'Hello'
```

### Generate a random string

```javascript
const generateRandomString = (length) =>
  [...Array(length)].map(() => Math.random().toString(36)[2]).join("");
```

#### Code Explanation

This code defines a function called `generateRandomString` that generates a random string of a specified `length`.

Here's a breakdown of how the code works:

1. `[...Array(length)]` creates an array of length `length` with empty slots.

2. `.map(() => Math.random().toString(36)[2])` maps over each element of the array and generates a random string character by calling `Math.random().toString(36)[2]`. The `Math.random()` function generates a random decimal between 0 and 1, `toString(36)` converts it to a base-36 string, and `[2]` selects the third character of the string.

3. `.join('')` joins all the generated random string characters together into a single string.

4. The final result, which is the randomly generated string of the specified `length`, is returned by the arrow function.

#### Usage

```javascript
console.log(generateRandomString(8)); // Outputs a random string of length 8
```

> Please note that this code assumes valid input values for `generateRandomString` function. It may throw errors or unexpected results if invalid inputs are provided.

### Generate a random number between two numbers

```javascript
const random = (min, max) => Math.floor(Math.random() * (max - min + 1) + min);
```

#### Code Explanation

This code defines a function called `random` that generates a random integer between the specified `min` and `max` values (inclusive).

Here's a breakdown of how the code works:

1. `Math.random()` generates a random decimal between 0 (inclusive) and 1 (exclusive).

2. `(max - min + 1)` calculates the range of possible values, including both `min` and `max`.

3. `Math.floor(...)` rounds down the result of the calculation to the nearest integer, ensuring that the generated random number is an integer.

4. The final result, which is the randomly generated integer within the specified range, is returned by the arrow function.

#### Usage

```javascript
console.log(random(1, 10)); // Outputs a random integer between 1 and 10 (inclusive)
```

### Clear all cookies

```javascript
const clearCookies = () =>
  document.cookie
    .split(";")
    .forEach(
      (cookie) =>
        (document.cookie = cookie
          .replace(/^ +/, "")
          .replace(/=.*/, `=;expires=${new Date(0).toUTCString()};path=/`))
    );
```

#### Code Explanation

This code defines a function called `clearCookies` that clears all cookies in the current browser session.

Here's a simplified explanation of how the code works:

1. `document.cookie` retrieves the current cookie string.

2. `.split(';')` splits the cookie string into individual cookies.

3. `.forEach(cookie => ...)` iterates over each cookie.

4. `cookie.replace(/^ +/, '')` removes leading whitespace from the cookie.

5. `.replace(/=.*/, `=;expires=${new Date(0).toUTCString()};path=/`)` replaces the cookie's value with an empty value and sets its expiration date to the past, effectively deleting the cookie.

By calling `clearCookies()`, all cookies will be cleared in the current browser session.

#### Usage

```javascript
clearCookies();
```

> It's important to note that manipulating and clearing cookies directly in JavaScript has limitations and considerations based on domain and security settings. Therefore, it's essential to use cookie operations responsibly and be aware of any potential implications.

### Scroll to top

```javascript
const goToTop = () => window.scrollTo(0, 0);
```

#### Code Explanation

This code defines a constant variable named `goToTop`, which is assigned an arrow function.

The arrow function has no parameters and consists of a single statement: `window.scrollTo(0, 0)`.

The `window.scrollTo()` method is used to scroll the window to a specified position. In this case, it is scrolling to the coordinates (0, 0), which represents the top-left corner of the window.

So, when the `goToTop` function is called, it will scroll the window to the top, bringing the top of the page into view.

#### Usage

```javascript
goToTop();
```

### Generate a random boolean

```javascript
const randomBoolean = () => Math.random() >= 0.5;
```

#### Code Explanation

This code defines a function called `randomBoolean` that returns a random boolean value.

Here's how it works:

- The `Math.random()` function generates a random decimal number between 0 (inclusive) and 1 (exclusive).
- The expression `Math.random() >= 0.5` compares the generated random number with 0.5. If the random number is greater than or equal to 0.5, it will evaluate to `true`; otherwise, it will evaluate to `false`.
- The function `randomBoolean` encapsulates this logic and returns the resulting boolean value.

In summary, when you call the `randomBoolean` function, it will generate a random boolean value with a roughly 50% chance of being `true` and a 50% chance of being `false`.

#### Usage

```javascript
randomBoolean();
```

### Identify the type of a data

```javascript
const typeOf = (data) =>
  Object.prototype.toString.call(data).slice(8, -1).toLowerCase();
```

#### Code Explanation

This code defines a function called `typeOf` that takes a parameter called `data`. This function determines the type of the `data` object and returns it as a lowercase string.

The code achieves this by using the `Object.prototype.toString.call(data)` method. This method returns a string representation of the object's type. By calling `slice(8, -1)` on the result, the code extracts the type portion from the string representation. Finally, `toLowerCase()` is used to convert the type string to lowercase.

#### Usage

```javascript
const myArray = [1, 2, 3];
const myObject = { name: "John", age: 25 };
const myFunction = () => {
  console.log("Hello!");
};

console.log(typeOf(myArray)); // Output: "array"
console.log(typeOf(myObject)); // Output: "object"
console.log(typeOf(myFunction)); // Output: "function"
console.log(typeOf(42)); // Output: "number"
console.log(typeOf("Hello")); // Output: "string"
console.log(typeOf(true)); // Output: "boolean"
```

### Calculate percent

```javascript
const calculatePercent = (value, total) => Math.round((value / total) * 100);
```

#### Code Explanation

This code defines a function called `calculatePercent` that takes two parameters: `value` and `total`. This function calculates the percentage of `value` relative to `total` and returns the result as a rounded whole number.

Here's a breakdown of the code:

1. `Math.round((value / total) * 100)`: This expression calculates the ratio of `value` to `total` by dividing `value` by `total` and then multiplying the result by 100 to get the percentage. The `Math.round()` function is used to round the result to the nearest whole number.

2. `const calculatePercent = (value, total) =>`: This line defines the `calculatePercent` function with two parameters: `value` and `total`. These parameters represent the values for which you want to calculate the percentage.

In summary, when you call the `calculatePercent` function with a specific `value` and `total`, it will calculate the percentage of `value` relative to `total` and return the result as a rounded whole number.

#### Usage

```javascript
const value = 75;
const total = 200;

const percentage = calculatePercent(value, total);
console.log(percentage); // Output: 38
```

### Get a random item of array

```javascript
const getRandomItem = (array) =>
  array[Math.floor(Math.random() * array.length)];
```

#### Code Explanation

This code defines a function called `getRandomItem` that takes an array as a parameter. The purpose of this function is to return a random item from the given array.

Here's how it works:

1. `Math.random()` generates a random floating-point number between 0 (inclusive) and 1 (exclusive).
2. `Math.random() * array.length` multiplies the random number by the length of the array. This will give a random number between 0 (inclusive) and the length of the array (exclusive).
3. `Math.floor()` rounds down the random number to the nearest whole number, ensuring it becomes a valid index within the range of the array indices.
4. `array[Math.floor(Math.random() * array.length)]` uses the calculated random index to retrieve the corresponding item from the array.
5. The retrieved item is then returned as the result of the function.

In summary, this code allows you to randomly select an item from an array by generating a random index and retrieving the corresponding item from that index.

#### Usage

```javascript
const fruits = ["apple", "banana", "orange", "grape", "kiwi"];
const randomFruit = getRandomItem(fruits);
console.log(randomFruit);
```

> please note that the code assumes that the input array is not empty.

### Sort array of objects based on the values of the specified key

```javascript
const sortBy = (arr, key) =>
  arr.sort((a, b) => (a[key] > b[key] ? 1 : a[key] < b[key] ? -1 : 0));
```

#### Code Explanation

This code defines a function called `sortBy` that takes an array (`arr`) and a key (`key`) as parameters. It sorts the array of objects based on the values of the specified key. The `sort()` method is used on the array, and a comparison function is provided as an argument.

The comparison function `(a, b) => a[key] > b[key] ? 1 : a[key] < b[key] ? -1 : 0` compares two objects `a` and `b` based on the values of the specified key. If the value of `a[key]` is greater than `b[key]`, it returns `1`, indicating that `a` should come after `b`. If the value of `a[key]` is less than `b[key]`, it returns `-1`, indicating that `a` should come before `b`. If the values are equal, it returns `0`, indicating that the order of `a` and `b` should remain unchanged.

By using this function, you can sort an array of objects based on a specific key in ascending order.

#### Usage

```javascript
const items = [
  { name: "Apple", price: 2.5 },
  { name: "Banana", price: 1.5 },
  { name: "Orange", price: 2.0 },
  { name: "Grape", price: 3.0 },
];

const sortedItems = sortBy(items, "price");
console.log(sortedItems); // [{ name: 'Banana', price: 1.5 }, { name: 'Orange', price: 2.0 }, { name: 'Apple', price: 2.5 }, { name: 'Grape', price: 3.0 }]
```

### Check if arrays / objects are equal

```javascript
const isEqual = (a, b) => JSON.stringify(a) === JSON.stringify(b);
```

#### Code Explanation

This code defines a function named `isEqual` that checks if two objects `a` and `b` are equal. It uses the `JSON.stringify` method to convert the objects to JSON strings and then compares the strings for equality using the `===` operator.

Here's a breakdown of the code:

1. `const isEqual = (a, b) =>`: This declares a function named `isEqual` with two parameters `a` and `b`. The function is defined using arrow function syntax.

2. `JSON.stringify(a)`: This converts the object `a` to a JSON string representation.

3. `JSON.stringify(b)`: This converts the object `b` to a JSON string representation.

4. `===`: This is the strict equality operator that checks if the two JSON strings are exactly equal, including their characters and order.

#### Usage

```javascript
const obj1 = { name: "John", age: 30 };
const obj2 = { name: "John", age: 30 };
const obj3 = { name: "Jane", age: 25 };

console.log(isEqual(obj1, obj2)); // true
console.log(isEqual(obj1, obj3)); // false
```

> While this approach may work for simple objects, it has limitations when dealing with complex objects or objects containing functions or circular references. The JSON.stringify method is not designed to handle all types of objects correctly. To properly check for object equality, you can use a deep comparison algorithm that traverses the object properties recursively.

### Add a new item to the array at the specified position

```javascript
const insert = (arr, index, newItem) => [
  ...arr.slice(0, index),
  newItem,
  ...arr.slice(index),
];
```

#### Code Explanation

This code defines a function called `insert` that takes three parameters: an array `arr`, an index `index`, and a new item `newItem`.

The function uses the spread syntax (`...`) to create a new array. Here's a breakdown of the code:

1. `arr.slice(0, index)`: This extracts a portion of the original array `arr` from the beginning (index `0`) up to, but not including, the specified `index`. It represents the elements that come before the insertion point.

2. `newItem`: This is the new item that you want to insert into the array.

3. `arr.slice(index)`: This extracts a portion of the original array `arr` starting from the specified `index` to the end. It represents the elements that come after the insertion point.

This code allows you to insert a new item into an array at a specific index while preserving the order of the existing elements.

#### Usage

```javascript
const myArray = [1, 2, 3, 4];
const newArray = insert(myArray, 2, "new item");

console.log(newArray); // [1, 2, "new item", 3, 4]
```

### Add commas to number

```javascript
const addCommasToNumber = (value) =>
  value.toString().replace(/(\d)(?=(\d{3})+\.)/g, "$1,");
```

#### Code Explanation

This code defines a function called `addCommasToNumber` that formats a numeric value by adding commas as thousands separators.

Here's a breakdown of the code:

1. The function takes a `value` parameter, which represents the numeric value to be formatted.

2. `value.toString()` converts the input value to a string.

3. The `replace()` method is called on the string representation of the value.

4. The regular expression `/(\d)(?=(\d{3})+\.)/g` is used to match a single digit (`\d`) that is followed by groups of three digits (`(\d{3})`) and a decimal point (`\.`).

5. The positive lookahead `(?=(\d{3})+\.)/g` ensures that the matching digit is followed by multiple groups of three digits and a decimal point, but it doesn't include these characters in the matched result.

6. In the replacement parameter `"$1,"`, the `$1` represents the matched digit captured in a group, and the comma is added after the matched digit.

7. The final result is a string representation of the value with commas added as thousands separators.

#### Usage

```javascript
console.log(addCommasToNumber(12345.6789)); // 12,345.6789
```
