## 1. Reverse a String

**Question:**

Write a function that takes a string as input and returns the string reversed.

**Solution:**

```javascript
function reverseString(str) {
  return str.split("").reverse().join("");
}

console.log(reverseString("hello"));
```

**Without In-Built method**

```js
function reverseString(str) {
  let reversed = "";

  for (let i = str.length - 1; i >= 0; i--) {
    reversed += str[i];
  }

  return reversed;
}

console.log(reverseString("hello"));
```

## 2. FizzBuzz

**Question:**

Write a function that prints numbers from 1 to 100. But for multiples of three, print "Fizz" instead of the number and for the multiples of five, print "Buzz". For numbers which are multiples of both three and five, print "FizzBuzz".

**Solution:**

```javascript
function fizzBuzz() {
  for (let i = 1; i <= 100; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
      console.log("FizzBuzz");
    } else if (i % 3 === 0) {
      console.log("Fizz");
    } else if (i % 5 === 0) {
      console.log("Buzz");
    } else {
      console.log(i);
    }
  }
}

fizzBuzz();
```

## 3. Find the Largest Number in an Array

**Question:**

Write a function to find the largest number in an array of numbers.

**Solution:**

```javascript
function findLargestNumber(arr) {
  return Math.max(...arr);
}

console.log(findLargestNumber([10, 5, 20, 15]));
```

**Without in-built method**

```javascript
function findLargestNumber(arr) {
  let largest = arr[0];

  for (let i = 1; i < arr.length; i++) {
    if (arr[i] > largest) {
      largest = arr[i];
    }
  }

  return largest;
}

console.log(findLargestNumber([10, 5, 20, 15]));
```

## 4. Check for Palindrome

**Question:**

Write a function that checks if a given string is a palindrome (a word, phrase, or sequence that reads the same backward as forward).

**Solution:**

```javascript
function isPalindrome(str) {
  const reversedStr = str.split("").reverse().join("");
  return str === reversedStr;
}

console.log(isPalindrome("racecar"));
console.log(isPalindrome("hello"));
```

**Without in-built method:**

```javascript
function isPalindrome(str) {
  let len = str.length;

  for (let i = 0; i < len / 2; i++) {
    if (str[i] !== str[len - 1 - i]) {
      return false;
    }
  }

  return true;
}

console.log(isPalindrome("racecar"));
console.log(isPalindrome("hello"));
```

## 5. Remove Duplicates from an Array

**Question:**

Write a function that removes duplicate values from an array.

**Solution:**

```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}

console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5]));
```

**Without in-built method:**

```javascript
function removeDuplicates(arr) {
  let uniqueArr = [];

  for (let i = 0; i < arr.length; i++) {
    let isDuplicate = false;

    for (let j = 0; j < uniqueArr.length; j++) {
      if (arr[i] === uniqueArr[j]) {
        isDuplicate = true;
        break;
      }
    }

    if (!isDuplicate) {
      uniqueArr.push(arr[i]);
    }
  }

  return uniqueArr;
}

console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5]));
```

## 6. Count Vowels in a String

**Question:**

Write a function that counts the number of vowels in a given string.

**Solution:**

```javascript
function countVowels(str) {
  const vowels = "aeiouAEIOU";
  let count = 0;

  for (let char of str) {
    if (vowels.includes(char)) {
      count++;
    }
  }

  return count;
}

console.log(countVowels("Hello World"));
```

**Without in-built method:**

```javascript
function countVowels(str) {
  let count = 0;

  for (let i = 0; i < str.length; i++) {
    let char = str[i].toLowerCase();

    if (
      char === "a" ||
      char === "e" ||
      char === "i" ||
      char === "o" ||
      char === "u"
    ) {
      count++;
    }
  }

  return count;
}

console.log(countVowels("Hello World"));
```

## 7. Sum of Array Elements

**Question:**

Write a function that calculates the sum of all elements in an array.

**Solution:**

```javascript
function sumArray(arr) {
  return arr.reduce((sum, num) => sum + num, 0);
}

console.log(sumArray([1, 2, 3, 4]));
```

**Without in-built method:**

```javascript
function sumArray(arr) {
  let sum = 0;

  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }

  return sum;
}

console.log(sumArray([1, 2, 3, 4]));
```

## 8. Factorial of a Number

**Question:**

Write a function that calculates the factorial of a given number.

**Solution:**

```javascript
function factorial(num) {
  if (num === 0 || num === 1) {
    return 1;
  } else {
    return num * factorial(num - 1);
  }
}

console.log(factorial(5));
```

## 9. Find Prime Numbers

**Question:**

Write a function that returns all prime numbers up to a given number.

**Solution:**

```javascript
function findPrimes(n) {
  const primes = [];
  for (let i = 2; i <= n; i++) {
    let isPrime = true;
    for (let j = 2; j <= Math.sqrt(i); j++) {
      if (i % j === 0) {
        isPrime = false;
        break;
      }
    }
    if (isPrime) {
      primes.push(i);
    }
  }
  return primes;
}

console.log(findPrimes(20));
```

## 10. Find the Fibonacci Sequence

**Question:**

Write a function that returns the first `n` Fibonacci numbers.

**Solution:**

```javascript
function fibonacci(n) {
  const fibSequence = [0, 1];
  for (let i = 2; i < n; i++) {
    fibSequence[i] = fibSequence[i - 1] + fibSequence[i - 2];
  }
  return fibSequence.slice(0, n);
}

console.log(fibonacci(10));
```

**Without in-built method:**

```javascript
function fibonacci(n) {
  let fibSequence = [];

  if (n >= 1) fibSequence.push(0);
  if (n >= 2) fibSequence.push(1);

  for (let i = 2; i < n; i++) {
    fibSequence.push(fibSequence[i - 1] + fibSequence[i - 2]);
  }

  return fibSequence;
}

console.log(fibonacci(10));
```

## 11. Flatten an Array

**Question:**

Write a function that takes a nested array and returns a flattened version of it.

**Solution:**

```javascript
function flattenArray(arr) {
  return arr.flat(Infinity);
}

console.log(flattenArray([1, [2, [3, [4]]]]));
```

**Without in-built method**

```javascript
function flattenArray(arr) {
  let flattened = [];

  // Loop through each element in the array
  for (let i = 0; i < arr.length; i++) {
    if (Array.isArray(arr[i])) {
      flattened = flattened.concat(flattenArray(arr[i]));
    } else {
      flattened.push(arr[i]);
    }
  }

  return flattened;
}

// Example usage:
console.log(flattenArray([1, [2, [3, [4]]]])); // Output: [1, 2, 3, 4]
```

## 12. Merge Two Sorted Arrays

**Question:**

Write a function that merges two sorted arrays into one sorted array.

**Solution:**

```javascript
function mergeSortedArrays(arr1, arr2) {
  let merged = [];
  let i = 0,
    j = 0;

  while (i < arr1.length && j < arr2.length) {
    if (arr1[i] < arr2[j]) {
      merged.push(arr1[i]);
      i++;
    } else {
      merged.push(arr2[j]);
      j++;
    }
  }

  return merged.concat(arr1.slice(i)).concat(arr2.slice(j));
}

console.log(mergeSortedArrays([1, 3, 5], [2, 4, 6]));
```

**Without in-built methods**

```javascript
function mergeSortedArrays(arr1, arr2) {
  let merged = [];
  let i = 0,
    j = 0;

  while (i < arr1.length && j < arr2.length) {
    if (arr1[i] < arr2[j]) {
      merged.push(arr1[i]);
      i++;
    } else {
      merged.push(arr2[j]);
      j++;
    }
  }

  while (i < arr1.length) {
    merged.push(arr1[i]);
    i++;
  }

  while (j < arr2.length) {
    merged.push(arr2[j]);
    j++;
  }

  return merged;
}

console.log(mergeSortedArrays([1, 3, 5], [2, 4, 6])); // Output: [1, 2, 3, 4, 5, 6]
```

## 13. Find the Missing Number in an Array

**Question:**

Write a function that finds the missing number in an array containing numbers from 1 to `n`.

**Solution:**

```javascript
function findMissingNumber(arr, n) {
  const totalSum = (n * (n + 1)) / 2;
  const arrSum = arr.reduce((sum, num) => sum + num, 0);
  return totalSum - arrSum;
}

console.log(findMissingNumber([1, 2, 4, 5], 5));
```

## 14. Find the Common Elements in Two Arrays

**Question:**

Write a function that finds the common elements between two arrays.

**Solution:**

```javascript
function findCommonElements(arr1, arr2) {
  return arr1.filter((value) => arr2.includes(value));
}

console.log(findCommonElements([1, 2, 3], [2, 3, 4]));
```

## 15. Capitalize the First Letter of Each Word

**Question:**

Write a function that capitalizes the first letter of each word in a given string.

**Solution:**

```javascript
function capitalizeWords(str) {
  return str
    .split(" ")
    .map((word) => word.charAt(0).toUpperCase() + word.slice(1))
    .join(" ");
}

console.log(capitalizeWords("hello world"));
```

## 16. Find the Longest Word in a String

**Question:**

Write a function that finds the longest word in a given string.

**Solution:**

```javascript
function findLongestWord(str) {
  return str
    .split(" ")
    .reduce(
      (longest, word) => (word.length > longest.length ? word : longest),
      ""
    );
}

console.log(findLongestWord("The quick brown fox jumped over the lazy dog"));
```

## 17. Convert a String to Title Case

**Question:**

Write a function that converts a string to title case, where the first and last letters of each word are capitalized.

**Solution:**

```javascript
function toTitleCase(str) {
  return str
    .split(" ")
    .map((word) => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase())
    .join(" ");
}

console.log(toTitleCase("the quick brown fox"));
```

## 18. Find the Index of the First Occurrence of a Substring

**Question:**

Write a function that finds the index of the first occurrence of a substring in a given string.

**Solution:**

```javascript
function indexOfSubstring(str, substr) {
  return str.indexOf(substr);
}

console.log(indexOfSubstring("hello world", "world"));
```

## 19. Calculate the Average of an Array of Numbers

**Question:**

Write a function that calculates the average of an array of numbers.

**Solution:**

```javascript
function calculateAverage(arr) {
  const sum = arr.reduce((total, num) => total + num, 0);
  return sum / arr.length;
}

console.log(calculateAverage([1, 2, 3, 4, 5]));
```

## 20. Generate a Random Integer Between Two Values

**Question:**

Write a function that generates a random integer between two given values (inclusive).

**Solution:**

```javascript
function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

console.log(getRandomInt(1, 10));
```

## 21. Find the Intersection of Two Arrays

**Question:**

Write a function that returns an array containing the elements that are present in both of the given arrays.

**Solution:**

```javascript
function intersectArrays(arr1, arr2) {
  return arr1.filter((value) => arr2.includes(value));
}

console.log(intersectArrays([1, 2, 3], [2, 3, 4]));
```

## 22. Remove All Falsey Values from an Array

**Question:**

Write a function that removes all falsey values (false, null, 0, "", undefined, and NaN) from an array.

**Solution:**

```javascript
function removeFalseyValues(arr) {
  return arr.filter(Boolean);
}

console.log(removeFalseyValues([0, 1, false, 2, "", 3]));
```

## 23. Convert an Array to an Object

**Question:**

Write a function that converts an array of key-value pairs into an object.

**Solution:**

```javascript
function arrayToObject(arr) {
  return arr.reduce((obj, [key, value]) => {
    obj[key] = value;
    return obj;
  }, {});
}

console.log(
  arrayToObject([
    ["name", "Alice"],
    ["age", 25],
  ])
);
```

## 24. Find the Second Largest Number in an Array

**Question:**

Write a function that finds the second largest number in an array of numbers.

**Solution:**

```javascript
function findSecondLargest(arr) {
  let first = -Infinity;
  let second = -Infinity;

  for (let num of arr) {
    if (num > first) {
      second = first;
      first = num;
    } else if (num > second && num < first) {
      second = num;
    }
  }

  return second;
}

// Example usage:
console.log(findSecondLargest([10, 5, 20, 15])); // Output: 15
```

## 25. Check if a Number is Prime

**Question:**

Write a function that checks if a given number is a prime number.

**Solution:**

```javascript
function isPrime(num) {
  if (num <= 1) return false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}

// Example usage:
console.log(isPrime(7)); // Output: true
console.log(isPrime(10)); // Output: false
```

## 26. Find the Longest Substring Without Repeating Characters

**Question:**

Write a function that finds the length of the longest substring without repeating characters in a given string.

**Solution:**

```javascript
function longestUniqueSubstring(str) {
  let longest = 0;
  let currentSubstring = "";

  for (let char of str) {
    const index = currentSubstring.indexOf(char);
    if (index !== -1) {
      currentSubstring = currentSubstring.slice(index + 1);
    }
    currentSubstring += char;
    longest = Math.max(longest, currentSubstring.length);
  }

  return longest;
}

// Example usage:
console.log(longestUniqueSubstring("abcabcbb")); // Output: 3
```

## 27. Sum of All Positive Numbers in an Array

**Question:**

Write a function that calculates the sum of all positive numbers in an array.

**Solution:**

```javascript
function sumPositiveNumbers(arr) {
  return arr.filter((num) => num > 0).reduce((sum, num) => sum + num, 0);
}

// Example usage:
console.log(sumPositiveNumbers([1, -2, 3, -4, 5])); // Output: 9
```

## 28. Count the Number of Words in a String

**Question:**

Write a function that counts the number of words in a given string.

**Solution:**

```javascript
function countWords(str) {
  return str.trim().split(/\s+/).length;
}

// Example usage:
console.log(countWords("The quick brown fox jumps over the lazy dog")); // Output: 9
```

## 29. Sort an Array of Objects by a Property

**Question:**

Write a function that sorts an array of objects by a given property.

**Solution:**

```javascript
function sortByProperty(arr, prop) {
  return arr
    .slice()
    .sort((a, b) => (a[prop] > b[prop] ? 1 : a[prop] < b[prop] ? -1 : 0));
}

// Example usage:
console.log(
  sortByProperty(
    [
      { name: "Alice", age: 30 },
      { name: "Bob", age: 25 },
    ],
    "age"
  )
);
// Output: [{ name: 'Bob', age: 25 }, { name: 'Alice', age: 30 }]
```

## 30. Generate a UUID

**Question:**

Write a function that generates a random UUID (Universally Unique Identifier).

**Solution:**

```javascript
function generateUUID() {
  return "xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx".replace(/[xy]/g, function (c) {
    const r = (Math.random() * 16) | 0;
    const v = c === "x" ? r : (r & 0x3) | 0x8;
    return v.toString(16);
  });
}

// Example usage:
console.log(generateUUID()); // Output: A random UUID, e.g., "e8a14a1d-98f4-4a0f-b007-7765699b0a5b"
```

## 31. Rotate Array Elements

**Question:**

Write a function that rotates the elements of an array to the right by a given number of positions.

**Solution:**

```javascript
function rotateArray(arr, positions) {
  const len = arr.length;
  positions = positions % len; // Handle cases where positions > len
  return arr.slice(-positions).concat(arr.slice(0, -positions));
}

// Example usage:
console.log(rotateArray([1, 2, 3, 4, 5], 2)); // Output: [4, 5, 1, 2, 3]
```

## 32. Find Duplicates in an Array

**Question:**

Write a function that finds all duplicate values in an array.

**Solution:**

```javascript
function findDuplicates(arr) {
  const seen = new Set();
  const duplicates = new Set();

  arr.forEach((item) => {
    if (seen.has(item)) {
      duplicates.add(item);
    } else {
      seen.add(item);
    }
  });

  return Array.from(duplicates);
}

// Example usage:
console.log(findDuplicates([1, 2, 3, 2, 4, 5, 1])); // Output: [1, 2]
```

## 33. Generate a Range of Numbers

**Question:**

Write a function that generates an array containing a range of numbers between two given values (inclusive).

**Solution:**

```javascript
function generateRange(start, end) {
  const range = [];
  for (let i = start; i <= end; i++) {
    range.push(i);
  }
  return range;
}

// Example usage:
console.log(generateRange(1, 5)); // Output: [1, 2, 3, 4, 5]
```

## 34. Merge Two Objects

**Question:**

Write a function that merges two objects into one, with the second object’s properties overwriting the first object’s properties in case of conflicts.

**Solution:**

```javascript
function mergeObjects(obj1, obj2) {
  return { ...obj1, ...obj2 };
}

// Example usage:
console.log(mergeObjects({ a: 1, b: 2 }, { b: 3, c: 4 })); // Output: { a: 1, b: 3, c: 4 }
```

## 35. Check if a String is a Valid Email Address

**Question:**

Write a function that checks if a given string is a valid email address.

**Solution:**

```javascript
function isValidEmail(email) {
  const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return re.test(email);
}

// Example usage:
console.log(isValidEmail("test@example.com")); // Output: true
console.log(isValidEmail("invalid-email")); // Output: false
```

## 36. Calculate the Factorial of a Number Iteratively

**Question:**

Write a function that calculates the factorial of a given number using an iterative approach.

**Solution:**

```javascript
function factorialIterative(num) {
  let result = 1;
  for (let i = 1; i <= num; i++) {
    result *= i;
  }
  return result;
}

// Example usage:
console.log(factorialIterative(5)); // Output: 120
```

## 37. Remove a Specific Element from an Array

**Question:**

Write a function that removes all instances of a specific value from an array.

**Solution:**

```javascript
function removeElement(arr, value) {
  return arr.filter((item) => item !== value);
}

// Example usage:
console.log(removeElement([1, 2, 3, 4, 2, 5], 2)); // Output: [1, 3, 4, 5]
```

## 38. Convert a Query String to an Object

**Question:**

Write a function that converts a query string into an object.

**Solution:**

```javascript
function queryStringToObject(query) {
  return query
    .slice(1) // Remove the leading "?"
    .split("&")
    .reduce((obj, pair) => {
      const [key, value] = pair.split("=");
      obj[decodeURIComponent(key)] = decodeURIComponent(value);
      return obj;
    }, {});
}

// Example usage:
console.log(queryStringToObject("?name=John&Doe&age=30")); // Output: { name: 'John', age: '30' }
```

## 39. Find the Median of an Array

**Question:**

Write a function that finds the median of an array of numbers.

**Solution:**

```javascript
function findMedian(arr) {
  const sorted = arr.slice().sort((a, b) => a - b);
  const middle = Math.floor(sorted.length / 2);

  if (sorted.length % 2 === 0) {
    return (sorted[middle - 1] + sorted[middle]) / 2;
  } else {
    return sorted[middle];
  }
}

// Example usage:
console.log(findMedian([1, 3, 2, 4])); // Output: 2.5
console.log(findMedian([1, 2, 3])); // Output: 2
```

## 40. Create a Deep Copy of an Object

**Question:**

Write a function that creates a deep copy of an object.

**Solution:**

```javascript
function deepCopy(obj) {
  return JSON.parse(JSON.stringify(obj));
}

// Example usage:
const original = { a: 1, b: { c: 2 } };
const copy = deepCopy(original);
console.log(copy); // Output: { a: 1, b: { c: 2 } }
console.log(copy !== original); // Output: true
console.log(copy.b !== original.b); // Output: true
```

## 41. Find the Most Frequent Element in an Array

**Question:**

Write a function that finds the most frequent element in an array.

**Solution:**

```javascript
function mostFrequentElement(arr) {
  const frequency = {};
  let maxCount = 0;
  let mostFrequent;

  arr.forEach((item) => {
    frequency[item] = (frequency[item] || 0) + 1;
    if (frequency[item] > maxCount) {
      maxCount = frequency[item];
      mostFrequent = item;
    }
  });

  return mostFrequent;
}

// Example usage:
console.log(mostFrequentElement([1, 2, 3, 2, 2, 3, 4])); // Output: 2
```

## 42. Convert a Date to a String in "YYYY-MM-DD" Format

**Question:**

Write a function that converts a JavaScript `Date` object to a string in the "YYYY-MM-DD" format.

**Solution:**

```javascript
function formatDate(date) {
  const year = date.getFullYear();
  const month = String(date.getMonth() + 1).padStart(2, "0");
  const day = String(date.getDate()).padStart(2, "0");

  return `${year}-${month}-${day}`;
}

// Example usage:
console.log(formatDate(new Date())); // Output: "2024-08-27" (or current date)
```

## 43. Check if a Number is Even or Odd

**Question:**

Write a function that checks if a number is even or odd.

**Solution:**

```javascript
function isEven(num) {
  return num % 2 === 0;
}

function isOdd(num) {
  return num % 2 !== 0;
}

// Example usage:
console.log(isEven(4)); // Output: true
console.log(isOdd(5)); // Output: true
```

## 44. Calculate the Sum of Digits of a Number

**Question:**

Write a function that calculates the sum of the digits of a given number.

**Solution:**

```javascript
function sumOfDigits(num) {
  return String(num)
    .split("")
    .reduce((sum, digit) => sum + Number(digit), 0);
}

// Example usage:
console.log(sumOfDigits(1234)); // Output: 10
```

## 45. Flatten an Array of Objects

**Question:**

Write a function that flattens an array of objects into a single object.

**Solution:**

```javascript
function flattenObjects(arr) {
  return arr.reduce((acc, obj) => ({ ...acc, ...obj }), {});
}

// Example usage:
console.log(flattenObjects([{ a: 1 }, { b: 2 }, { c: 3 }])); // Output: { a: 1, b: 2, c: 3 }
```

## 46. Check if Two Strings are Anagrams

**Question:**

Write a function that checks if two given strings are anagrams of each other.

**Solution:**

```javascript
function areAnagrams(str1, str2) {
  const normalize = (str) =>
    str.replace(/\s+/g, "").toLowerCase().split("").sort().join("");
  return normalize(str1) === normalize(str2);
}

// Example usage:
console.log(areAnagrams("listen", "silent")); // Output: true
console.log(areAnagrams("hello", "world")); // Output: false
```

## 47. Create a Debounce Function

**Question:**

Write a function that creates a debounce function to limit how often a function can be executed.

**Solution:**

```javascript
function debounce(func, wait) {
  let timeout;
  return function (...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(this, args), wait);
  };
}

// Example usage:
const debouncedLog = debounce(() => console.log("Debounced!"), 1000);
debouncedLog();
```

## 48. Remove All Occurrences of a Value from an Object

**Question:**

Write a function that removes all occurrences of a specific value from an object (including nested objects).

**Solution:**

```javascript
function removeValue(obj, valueToRemove) {
  const remove = (obj) => {
    for (const key in obj) {
      if (obj[key] === valueToRemove) {
        delete obj[key];
      } else if (typeof obj[key] === "object" && obj[key] !== null) {
        remove(obj[key]);
      }
    }
  };

  remove(obj);
  return obj;
}

// Example usage:
const data = { a: 1, b: { c: 1, d: 2 }, e: 1 };
console.log(removeValue(data, 1)); // Output: { b: { d: 2 } }
```

## 49. Find the Intersection of Multiple Arrays

**Question:**

Write a function that finds the common elements across multiple arrays.

**Solution:**

```javascript
function intersectionOfArrays(...arrays) {
  return arrays.reduce((acc, arr) => acc.filter((item) => arr.includes(item)));
}

// Example usage:
console.log(intersectionOfArrays([1, 2, 3], [2, 3, 4], [3, 4, 5])); // Output: [3]
```

## 50. Generate a Random Hex Color

**Question:**

Write a function that generates a random hexadecimal color code.

**Solution:**

```javascript
function getRandomHexColor() {
  return (
    "#" +
    Math.floor(Math.random() * 0xffffff)
      .toString(16)
      .padStart(6, "0")
  );
}

// Example usage:
console.log(getRandomHexColor()); // Output: A random hex color code, e.g., "#a3c2f7"
```

## 51. Convert an Object to a Query String

**Question:**

Write a function that converts an object into a query string.

**Solution:**

```javascript
function objectToQueryString(obj) {
  return Object.keys(obj)
    .map((key) => `${encodeURIComponent(key)}=${encodeURIComponent(obj[key])}`)
    .join("&");
}

// Example usage:
console.log(objectToQueryString({ name: "Alice", age: 30 })); // Output: "name=Alice&age=30"
```

## 52. Count Vowels in a String

**Question:**

Write a function that counts the number of vowels in a given string.

**Solution:**

```javascript
function countVowels(str) {
  return (str.match(/[aeiou]/gi) || []).length;
}

// Example usage:
console.log(countVowels("Hello World")); // Output: 3
```

## 53. Remove Duplicates from an Array

**Question:**

Write a function that removes duplicate values from an array.

**Solution:**

```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}

// Example usage:
console.log(removeDuplicates([1, 2, 3, 2, 4, 1])); // Output: [1, 2, 3, 4]
```

## 54. Find the Difference Between Two Arrays

**Question:**

Write a function that finds the difference between two arrays (elements that are in the first array but not in the second).

**Solution:**

```javascript
function difference(arr1, arr2) {
  return arr1.filter((item) => !arr2.includes(item));
}

// Example usage:
console.log(difference([1, 2, 3, 4], [2, 4])); // Output: [1, 3]
```

## 55. Reverse a String

**Question:**

Write a function that reverses a given string.

**Solution:**

```javascript
function reverseString(str) {
  return str.split("").reverse().join("");
}

// Example usage:
console.log(reverseString("hello")); // Output: "olleh"
```

## 56. Check if a Number is Palindrome

**Question:**

Write a function that checks if a number is a palindrome (reads the same backward as forward).

**Solution:**

```javascript
function isPalindromeNumber(num) {
  const str = num.toString();
  return str === str.split("").reverse().join("");
}

// Example usage:
console.log(isPalindromeNumber(121)); // Output: true
console.log(isPalindromeNumber(123)); // Output: false
```

## 57. Merge Two Arrays Alternately

**Question:**

Write a function that merges two arrays by alternating elements from each array.

**Solution:**

```javascript
function mergeAlternately(arr1, arr2) {
  const result = [];
  const len = Math.max(arr1.length, arr2.length);

  for (let i = 0; i < len; i++) {
    if (i < arr1.length) result.push(arr1[i]);
    if (i < arr2.length) result.push(arr2[i]);
  }

  return result;
}

// Example usage:
console.log(mergeAlternately([1, 2, 3], ["a", "b", "c", "d"])); // Output: [1, 'a', 2, 'b', 3, 'c', 'd']
```

## 58. Count the Number of Occurrences of a Character in a String

**Question:**

Write a function that counts the number of times a specific character appears in a string.

**Solution:**

```javascript
function countCharacter(str, char) {
  return str.split(char).length - 1;
}

// Example usage:
console.log(countCharacter("hello world", "o")); // Output: 2
```

## 59. Find the Greatest Common Divisor (GCD) of Two Numbers

**Question:**

Write a function that finds the greatest common divisor (GCD) of two numbers using the Euclidean algorithm.

**Solution:**

```javascript
function gcd(a, b) {
  while (b !== 0) {
    [a, b] = [b, a % b];
  }
  return a;
}

// Example usage:
console.log(gcd(48, 18)); // Output: 6
```

## 60. Validate a Palindrome String

**Question:**

Write a function that checks if a given string is a palindrome (reads the same backward as forward), considering only alphanumeric characters and ignoring cases.

**Solution:**

```javascript
function isValidPalindrome(str) {
  const cleaned = str.replace(/[^a-zA-Z0-9]/g, "").toLowerCase();
  return cleaned === cleaned.split("").reverse().join("");
}

// Example usage:
console.log(isValidPalindrome("A man, a plan, a canal: Panama")); // Output: true
console.log(isValidPalindrome("race a car")); // Output: false
```
