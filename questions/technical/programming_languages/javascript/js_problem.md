
## 1. Reverse a String

**Question:**

Write a function that takes a string as input and returns the string reversed.

**Solution:**

```javascript
function reverseString(str) {
  return str.split('').reverse().join('');
}

// Example usage:
console.log(reverseString("hello")); // Output: "olleh"
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

// Example usage:
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

// Example usage:
console.log(findLargestNumber([10, 5, 20, 15])); // Output: 20
```

## 4. Check for Palindrome

**Question:**

Write a function that checks if a given string is a palindrome (a word, phrase, or sequence that reads the same backward as forward).

**Solution:**

```javascript
function isPalindrome(str) {
  const reversedStr = str.split('').reverse().join('');
  return str === reversedStr;
}

// Example usage:
console.log(isPalindrome("racecar")); // Output: true
console.log(isPalindrome("hello"));   // Output: false
```

## 5. Remove Duplicates from an Array

**Question:**

Write a function that removes duplicate values from an array.

**Solution:**

```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}

// Example usage:
console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5])); // Output: [1, 2, 3, 4, 5]
```

## 6. Count Vowels in a String

**Question:**

Write a function that counts the number of vowels in a given string.

**Solution:**

```javascript
function countVowels(str) {
  const vowels = 'aeiouAEIOU';
  let count = 0;

  for (let char of str) {
    if (vowels.includes(char)) {
      count++;
    }
  }

  return count;
}

// Example usage:
console.log(countVowels("Hello World")); // Output: 3
```

## 7. Sum of Array Elements

**Question:**

Write a function that calculates the sum of all elements in an array.

**Solution:**

```javascript
function sumArray(arr) {
  return arr.reduce((sum, num) => sum + num, 0);
}

// Example usage:
console.log(sumArray([1, 2, 3, 4])); // Output: 10
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

// Example usage:
console.log(factorial(5)); // Output: 120
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

// Example usage:
console.log(findPrimes(20)); // Output: [2, 3, 5, 7, 11, 13, 17, 19]
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

// Example usage:
console.log(fibonacci(10)); // Output: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```


## 11. Flatten an Array

**Question:**

Write a function that takes a nested array and returns a flattened version of it.

**Solution:**

```javascript
function flattenArray(arr) {
  return arr.flat(Infinity);
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
  let i = 0, j = 0;

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

// Example usage:
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

// Example usage:
console.log(findMissingNumber([1, 2, 4, 5], 5)); // Output: 3
```

## 14. Find the Common Elements in Two Arrays

**Question:**

Write a function that finds the common elements between two arrays.

**Solution:**

```javascript
function findCommonElements(arr1, arr2) {
  return arr1.filter(value => arr2.includes(value));
}

// Example usage:
console.log(findCommonElements([1, 2, 3], [2, 3, 4])); // Output: [2, 3]
```

## 15. Capitalize the First Letter of Each Word

**Question:**

Write a function that capitalizes the first letter of each word in a given string.

**Solution:**

```javascript
function capitalizeWords(str) {
  return str.split(' ').map(word => word.charAt(0).toUpperCase() + word.slice(1)).join(' ');
}

// Example usage:
console.log(capitalizeWords("hello world")); // Output: "Hello World"
```

## 16. Find the Longest Word in a String

**Question:**

Write a function that finds the longest word in a given string.

**Solution:**

```javascript
function findLongestWord(str) {
  return str.split(' ').reduce((longest, word) => word.length > longest.length ? word : longest, '');
}

// Example usage:
console.log(findLongestWord("The quick brown fox jumped over the lazy dog")); // Output: "jumped"
```

## 17. Convert a String to Title Case

**Question:**

Write a function that converts a string to title case, where the first and last letters of each word are capitalized.

**Solution:**

```javascript
function toTitleCase(str) {
  return str.split(' ').map(word => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase()).join(' ');
}

// Example usage:
console.log(toTitleCase("the quick brown fox")); // Output: "The Quick Brown Fox"
```

## 18. Find the Index of the First Occurrence of a Substring

**Question:**

Write a function that finds the index of the first occurrence of a substring in a given string.

**Solution:**

```javascript
function indexOfSubstring(str, substr) {
  return str.indexOf(substr);
}

// Example usage:
console.log(indexOfSubstring("hello world", "world")); // Output: 6
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

// Example usage:
console.log(calculateAverage([1, 2, 3, 4, 5])); // Output: 3
```

## 20. Generate a Random Integer Between Two Values

**Question:**

Write a function that generates a random integer between two given values (inclusive).

**Solution:**

```javascript
function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

// Example usage:
console.log(getRandomInt(1, 10)); // Output: A random integer between 1 and 10
```

