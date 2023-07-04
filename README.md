# JavaScript One-line Utility Codes

![JavaScript One-line Utility Codes](./assets/cover.png)

If you like this content, you can ping me or follow me on Twitter 👊

[![Twitter URL](https://img.shields.io/twitter/url?url=https%3A%2F%2Ftwitter.com%2Fmkazemiraz&style=social&logo=twitter&label=Follow%20%40mkazemiraz)](https://twitter.com/mkazemiraz)

## Introduction

😍 Welcome to the JavaScript One-Line Utility Codes repository! Here, we aim to provide you with a curated collection of powerful and concise JavaScript utility functions that can be written in just one line of code.

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
