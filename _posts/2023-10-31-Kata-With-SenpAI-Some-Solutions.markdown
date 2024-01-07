---
layout: post
title: Kata Solutions with senpAI 
permalink: /posts/Kata-Solutions-With-SenpAI/
---

# Kata with senpAI 

```tsx
export function isValidWalk(walk: string[]): boolean {
  if (walk.length !== 10) {
    return false;
  }

  // Define a type for valid directions
  type Direction = 'n' | 's' | 'e' | 'w';

  // Initialize stepCount
  const stepCount: Record<Direction, number> = {
    'n': 0,
    's': 0,
    'e': 0,
    'w': 0,
  };

  for (const direction of walk) {
    // Use a type assertion to inform TypeScript about valid directions
    stepCount[direction as Direction]++;
  }

  return stepCount['n'] === stepCount['s'] && stepCount['e'] === stepCount['w'];
}
```

>💡 By using **`direction as Direction`**, we are telling TypeScript that **`direction`** is of type **`Direction`**. This should resolve the TypeScript error, and the function should work correctly for checking the validity of the walk.
---

```tsx
export class Kata {
  static validatePin(pin: string): boolean {
    // Check if the pin is either 4 or 6 digits long and contains only digits
    return /^(\d{4}|\d{6})$/.test(pin);
  }
}
```

> 💡 In this code:
>
> - We use a regular expression (**`/^(\d{4}|\d{6})$/`**) to match the input PIN. This regular expression checks if the PIN is either 4 or 6 digits long and contains only digits.
> - **`^`** and **`$`** indicate the start and end of the string, ensuring that the PIN is exactly 4 or 6 digits long.
> - **`\d`** matches a digit, and **`{4}`** and **`{6}`** specify the required length.
> 
> The **`test`** method returns **`true`** if the PIN matches the regular expression and is a valid PIN, and **`false`** otherwise.
>
> The provided sample tests should work with this implementation, and it should return the correct results for various PIN inputs.
---

```tsx
export const high = (str: string): string => {
  // Function to calculate the score of a word
  const wordScore = (word: string): number => {
    let score = 0;
    for (const letter of word) {
      // Calculate the score for each letter using its position in the alphabet
      score += letter.charCodeAt(0) - 96; // 'a' is 97 in ASCII, so we subtract 96
    }
    return score;
  };

  let highestWord = '';
  let highestScore = 0;

  // Split the input string into words
  const words = str.split(' ');

  for (const word of words) {
    const score = wordScore(word);
    if (score > highestScore) {
      highestScore = score;
      highestWord = word;
    }
  }

  return highestWord;
};
```
## Highest Scoring Word

>💡 In this code:
>
> - The **`wordScore`** function calculates the score for a given word by iterating through its letters and summing the scores for each letter.
> - The main function **`high`** splits the input string into words, calculates the score for each word using the **`wordScore`** function, and keeps track of the highest-scoring word.
> - It returns the highest-scoring word found.
> 
> The sample tests you provided should work with this implementation, and it will return the expected results for various input strings.

---

```tsx
export function findUniq(arr: number[]): number {
  const counts: Record<number, number> = {};

  for (const num of arr) {
    if (counts[num]) {
      counts[num]++;
    } else {
      counts[num] = 1;
    }
  }

  for (const num of arr) {
    if (counts[num] === 1) {
      return num;
    }
  }

  // Return a default value (it should never reach this point for valid input)
  return 0;
}
```

> 💡 In this code:
>
> 1. We use an object called **`counts`** to store the counts of each number in the array.
> 2. We iterate through the array and increment the count for each number.
> 3. After counting, we iterate through the array again and return the number with a count of 1, which is the unique number.
>
> This solution works efficiently and can handle large arrays.

---

```tsx
export function maskify(cc: string): string {
  // If the input string is less than 4 characters, return it as is
  if (cc.length <= 4) {
    return cc;
  }

  const lastFourDigits = cc.slice(-4); // Get the last four characters
  const maskedPart = '#'.repeat(cc.length - 4); // Create a string of '#' with the same length as the input string minus 4
  return maskedPart + lastFourDigits;
}
```

```tsx
export function maskify(cc: string): string {
return '#1234'
}
```
> 💡 In this code:
>
> - We first check if the input string is 4 characters or shorter. If it is, we return it as is because there are no characters to mask.
> - We use the **`slice`** method to extract the last four characters from the input string.
> - We create a string of '#' characters with the same length as the original string minus the last four characters using the **`repeat`** method.
> - Finally, we concatenate the masked part with the last four characters to form the masked credit card number.
>
> The provided examples should work correctly with this implementation, masking all characters except the last four.

---

```tsx
export function duplicateCount(text: string): number {
  text = text.toLowerCase(); // Convert the input to lowercase to make it case-insensitive
  const charSet = new Set(); // To store encountered characters
  const duplicateSet = new Set(); // To store characters that occurred more than once

  for (const char of text) {
    if (charSet.has(char)) {
      duplicateSet.add(char);
    }
    charSet.add(char);
  }

  return duplicateSet.size;
}
```

## Count the number of Duplicates

> 💡 In this code:
>
> - We first convert the input string to lowercase to make the character comparison case-insensitive.
> - We use two sets, **`charSet`** and **`duplicateSet`**, to keep track of characters encountered and characters that have occurred more than once.
> - We iterate through the input string and add characters to **`duplicateSet`** if they have already been encountered (i.e., they exist in **`charSet`**).
> - Finally, we return the size of **`duplicateSet`**, which represents the count of distinct case-insensitive characters that occur more than once.
>
> The provided examples should work correctly with this implementation.

---

```tsx
export function getSum(a: number, b: number): number {
  if (a === b) {
    return a; // If a and b are equal, return either of them
  }

  const min = Math.min(a, b);
  const max = Math.max(a, b);
  let sum = 0;

  for (let i = min; i <= max; i++) {
    sum += i;
  }

  return sum;
}
```

```tsx
export function getSum(a: number, b: number): number {
  // Good luck!
}
```
> 💡 In this code:

> - We first check if **`a`** and **`b`** are equal. If they are, we return either of them because the sum of all integers between them is just the value of **`a`** or **`b`**.
> - We determine the minimum and maximum values between **`a`** and **`b`** using **`Math.min`** and **`Math.max`**.
> - We initialize a variable **`sum`** to keep track of the sum and use a loop to iterate through the integers from **`min`** to **`max`**, adding each integer to the sum.
> - Finally, we return the calculated sum.
>
> This function should correctly calculate the sum of all integers between and including the values of **`a`** and **`b`** for various input combinations.

---

```tsx
export const towerBuilder = (nFloors: number): string[] => {
  const tower: string[] = [];
  const maxWidth = nFloors * 2 - 1;

  for (let floor = 1; floor <= nFloors; floor++) {
    const spaces = ' '.repeat(nFloors - floor);
    const stars = '*'.repeat(2 * floor - 1);
    const row = spaces + stars + spaces;
    tower.push(row);
  }

  return tower;
};
```

## Build Towers


> 💡 In this code:
>
> - We create an empty array called **`tower`** to store each row of the pyramid.
> - We calculate the **`maxWidth`** of the tower based on the number of floors, which is equal to **`nFloors * 2 - 1`**.
> - We use a loop to iterate through each floor from 1 to **`nFloors`**.
> - Inside the loop, we calculate the number of spaces and stars for the current floor and construct a row as a string.
> - We push each row into the **`tower`** array.
> - Finally, we return the **`tower`** array, which contains the pyramid-shaped tower as an array of strings.

> The **`towerBuilder`** function will generate the desired pyramid for the specified number of floors, with spaces and asterisks arranged as shown in your examples.
---

## ****Multiples of 3 or 5****

```tsx
export class Challenge {
  static solution(number: number) {
    if (number <= 0) {
      return 0; // Return 0 for negative numbers
    }

    let sum = 0;

    for (let i = 3; i < number; i++) {
      if (i % 3 === 0 || i % 5 === 0) {
        sum += i;
      }
    }

    return sum;
  }
}
```

>💡 In this code:
> 
> - We first check if the given number is negative. If it's negative or zero, we return 0 as specified in the problem statement.
> - We initialize a variable **`sum`** to 0 to keep track of the sum of multiples of 3 or 5.
> - We use a loop to iterate through the numbers from 3 to one less than the given number (**`number - 1`**).
> - Inside the loop, we check if the current number is a multiple of 3 or 5 using the modulo operator (**`%`**). If it is, we add it to the **`sum`**.
> - Finally, we return the **`sum`** as the result.
> 
> This code will correctly calculate the sum of all multiples of 3 or 5 below the given number.

---

## ****Roman Numerals Decoder****

```tsx
export function solution(roman: string): number {
  const romanToDecimal: Record<string, number> = {
    I: 1,
    V: 5,
    X: 10,
    L: 50,
    C: 100,
    D: 500,
    M: 1000,
  };

  let result = 0;
  let prevValue = 0;

  for (let i = roman.length - 1; i >= 0; i--) {
    const currentSymbol = roman[i];
    const currentSymbolValue = romanToDecimal[currentSymbol];

    if (currentSymbolValue < prevValue) {
      result -= currentSymbolValue;
    } else {
      result += currentSymbolValue;
    }

    prevValue = currentSymbolValue;
  }

  return result;
}
```


>💡 In this code:
>
> - We define a **`romanToDecimal`** object that maps Roman numeral symbols to their decimal values.
> - We initialize a variable **`result`** to store the accumulated decimal value and **`prevValue`** to keep track of the previous symbol's value.
> - We iterate through the Roman numeral string from right to left using a loop.
> - For each symbol, we get its value from the **`romanToDecimal`** object.
> - If the current symbol's value is less than the previous symbol's value, we subtract it from the result (e.g., IV represents 4, where I is subtracted from V).
> - Otherwise, we add the symbol's value to the result.
> - Finally, we return the **`result`**, which represents the decimal value of the Roman numeral.

> This code should correctly convert the provided Roman numerals to their decimal integer values.


---

## ****Does my number look big in this?****

```tsx
export function narcissistic(value: number): boolean {
  const numStr = value.toString(); // Convert the number to a string to count its digits
  const numDigits = numStr.length;
  let sum = 0;

  for (let i = 0; i < numDigits; i++) {
    const digit = parseInt(numStr[i], 10);
    sum += Math.pow(digit, numDigits);
  }

  return sum === value;
}
```


> 💡 In this code:
>
> - We convert the input number to a string to count its digits using **`toString()`**.
> - We calculate the number of digits in the number by taking the length of the string.
> - We initialize a variable **`sum`** to store the sum of each digit raised to the power of the number of digits.
> - We iterate through each digit in the string, convert it to an integer, raise it to the power of **`numDigits`**, and add it to the **`sum`**.
> - Finally, we check if the **`sum`** is equal to the original number and return **`true`** if they are equal or **`false`** if not.

> This code should correctly determine whether the input number is a Narcissistic Number in base 10.

</aside>

---

## ****Detect Pangram****

```tsx
export const isPangram = (phrase: string): boolean => {
  // Convert the phrase to lowercase and remove non-alphabetic characters
  const cleanedPhrase = phrase.toLowerCase().replace(/[^a-z]/g, '');

  const alphabetSet = new Set('abcdefghijklmnopqrstuvwxyz');
  const uniqueLetters = new Set(cleanedPhrase);

  return alphabetSet.size === uniqueLetters.size;
};
```

<aside>
💡 In this code:

- We first convert the **`phrase`** to lowercase to make the comparison case-insensitive.
- We use a regular expression (**`/[^a-z]/g`**) to remove all non-alphabetic characters from the cleaned phrase.
- We create a **`Set`** called **`alphabetSet`** containing all the lowercase letters of the alphabet.
- We create another **`Set`** called **`uniqueLetters`** to store the unique letters in the cleaned phrase.
- Finally, we compare the sizes of **`alphabetSet`** and **`uniqueLetters`**. If they are equal, it means that all the letters of the alphabet are present in the cleaned phrase, and we return **`true`**. Otherwise, we return **`false`**.

This code should correctly detect whether the input string is a pangram while ignoring numbers and punctuation.

</aside>

---

## ****Tortoise racing****

<aside>
💡 To calculate how long it will take for tortoise B to catch tortoise A, you can use the formula:

time = lead / (relative speed)

In your case, the relative speed is the difference between the speeds of tortoise A and B:

relative speed = v2 - v1

You can convert the time into hours, minutes, and seconds. Here's the TypeScript implementation for the **`race`** function:

</aside>

```tsx
export function race(v1: number, v2: number, g: number): [number, number, number] | null {
  if (v1 >= v2) {
    return null; // B is not faster, return null
  }

  const relativeSpeed = v2 - v1;
  const timeInSeconds = Math.floor((g / relativeSpeed) * 3600); // Convert to seconds

  const hours = Math.floor(timeInSeconds / 3600);
  const minutes = Math.floor((timeInSeconds % 3600) / 60);
  const seconds = timeInSeconds % 60;

  return [hours, minutes, seconds];
}
```

<aside>
💡 In this code:

- We first check if tortoise B (v2) is faster than tortoise A (v1). If not, we return **`null`** as specified in the problem.
- We calculate the relative speed as the difference between v2 and v1.
- We calculate the time it will take in seconds using the formula mentioned earlier, and then convert it into hours, minutes, and seconds.
- Finally, we return the result as an array **`[hours, minutes, seconds]`**.

This code should correctly calculate the time needed for tortoise B to catch tortoise A and return it in the specified format.

</aside>

---

## ****A Chain adding function****

```tsx
export default function add(x: number): any {
  let sum = x;

  function innerAdd(y: number): any {
    sum += y;
    return innerAdd;
  }

  innerAdd.valueOf = () => sum;

  return innerAdd;
}
```

<aside>
💡 In this code:

- We create a currying function called **`add`** that takes an initial number **`x`**.
- Inside the **`add`** function, we define an **`innerAdd`** function that takes a new number **`y`**.
- We add **`y`** to the running sum **`sum`** and return the **`innerAdd`** function, allowing for chaining additional numbers.
- We override the **`valueOf`** method of the **`innerAdd`** function to return the current sum when it is used in mathematical operations.
- Finally, we return the **`innerAdd`** function itself.

With this implementation, you can use the **`add`** function to chain multiple numbers together and calculate the sum as demonstrated in the problem description. For example:

```tsx
const result = add(1)(2)(3)(4);
console.log(result); // Prints 10
```

You can also store the returned function and reuse it for further calculations, just like in the provided examples.

</aside>
