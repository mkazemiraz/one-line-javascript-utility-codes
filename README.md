# JavaScript One-line Utility Codes

![One-line JavaScript Utility Codes](./assets/cover.png)

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

### Copy text to clipboard

```javascript
const copyToClipboard = (text) => navigator.clipboard.writeText(text);
```

#### Code Explanation

The code snippet provided defines a JavaScript function called `copyToClipboard` that takes a text parameter. The purpose of this function is to copy the specified `text` to the user's clipboard.

The function utilizes the `navigator.clipboard.writeText()` method, which is a built-in browser API for writing text to the clipboard. This method takes the `text` parameter as input and attempts to write it to the clipboard.

By encapsulating this functionality in a concise one-liner, the `copyToClipboard` function provides a convenient and reusable way to copy text to the clipboard in JavaScript applications.

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

> Please note that this code assumes valid input values for `dayDiff` function.It may throw errors or unexpected results if invalid inputs are provided.
