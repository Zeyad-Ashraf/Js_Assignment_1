// Assignment 1

// 1. Create a function that calculates the sum of two given numbers.
// Input: 3, 5
// Output: 8

function calcSumOfTwoNumbers(numberOne,numberTwo) {
    return numberOne + numberTwo;
}
console.log(calcSumOfTwoNumbers(5, 3));

// 2. Write a function that checks if a number is prime (a number that can only be divided
// by 1 and itself without any remainder).
// Input: 7
// Output: true

function primeNumbers(prime) {
    let isPrime = true;
    for (let i = 2; i <= prime / 2; i++){
        if (prime % i == 0) {
            isPrime = false;
            break;
        }
    }
    return isPrime;
}
console.log(primeNumbers(7));

// 3. Write a function to reverse a given string (using built in method).
// Input: "hello"
// Output: "olleh"

function reverseStrings(string) {
    return string.split("").reverse().join("");
}
console.log(reverseStrings("hello"));

// 4. Write a function to find the largest number in an array.
// Input: [1, 3, 7, 2, 4]
// Output: 7

function largestNumber(arrOfNum) {
    return Math.max(...arrOfNum);
}
console.log(largestNumber([1, 3, 7, 2, 4]));

// 5. Write a function that filters an array and returns only the even numbers.
// Input: [1, 2, 3, 4, 5, 6]
// Output: [2, 4, 6]

function evenNumbers(array) {
    return array.filter((el) => el % 2 == 0);
}
console.log(evenNumbers([1, 2, 3, 4, 5, 6]));

// 6. Implement a function to reverse a string without using the built-in reverse() method.
// Input: "route"
// Output: "etuor"

function reverseWithoutMethod(string) {
    let str = "";
    for (let i = string.length-1; i >= 0; i--)
        str += string[i];
    return str;
}
console.log(reverseWithoutMethod("hello"));

// 7. Write a function to calculate the average value of all numbers in an array.
// Input: [1, 2, 3, 4, 5]
// Output: 3

function calcAverage(array) {
    let sum = 0;
    for (let i = 0; i < array.length; i++)
        sum += array[i];
    return sum;
}
console.log(calcAverage([1, 2, 3, 4, 5]));

// 8. Write a function that determines whether a given day number (1-7) represents a
// weekday or weekend.
// Input: 5
// Output: "Weekday"
// Input: 7
// Output: "Weekend"

let weekendOrWeekday = (number) => number === 7 ? "Weekend" : "Weekday";
console.log(weekendOrWeekday(7));

// 9. Write a function that filters an array of numbers and returns only those that are divisible
// by 2 or 3.
// Input: [1, 2, 3, 4, 5, 6, 7, 8, 9]
// Output: [2, 3, 4, 6, 8, 9]

let numberDivisible = (array) => array.filter((el) => (el % 2 == 0 || el % 3 == 0));
console.log(numberDivisible([1, 2, 3, 4, 5, 6, 7, 8, 9]));

// 10. Write a function that finds the index of a given element in an array. If the element isn't
// found, return `-1`.
// Input: [1, 2, 3, 4, 5], 3
// Output: 2
// Input: [1, 2, 3, 4, 5], 10
// Output: -1

let indexOfElement = function (array,element) {
    return array.includes(element) ? array.indexOf(element) : -1;
}
console.log(indexOfElement([1, 2, 3, 4, 5], 3));
console.log(indexOfElement([1, 2, 3, 4, 5], 10));

// 11. Write a function to calculate the factorial of a given number.
// Input: 5
// Output: 120

// solve with Recursive function 
let sum = 1;
function factorial(number) {
    if (number == 1)
        return 1;
    return factorial(number - 1) * number;
}
console.log(factorial(5));

// solve with simple for loop
function factorialTwo(number) {
    let sum = 1;
    for (let i = 1; i <= number; i++)
        sum *= i;
    return sum;
}
console.log(factorialTwo(5));

// 12. Write a function that takes an object and returns an array containing only its keys.
// Input: {name: "John", age: 30}
// Output: ["name", "age"]

function objectKeys(prameter) {
    let object = prameter, arr = [], keyLength = Object.keys(object).length;
    for (let i = 0; i < keyLength; i++)
        arr[i] = Object.keys(object)[i];
    return arr;
}
console.log(objectKeys({ name: "John", age: 30 }))

// 13. Write a function that returns only the unique numbers from an array.
// Input: [1, 2, 2, 3, 4, 4, 5]
// Output: [1, 3, 5]

function uniqueNumbers(array) {
    let arr = [];
    for (let i = 0; i < array.length; i++){
        if (array.indexOf(array[i]) === array.lastIndexOf(array[i]))
            arr.push(array[i]);
    }
    return arr;
}
console.log(uniqueNumbers([1, 2, 2, 3, 4, 4, 5]));

// 14. Write a function to count the occurrences of each character in a string.
// Input: "hello"
// Output: {h: 1, e: 1, l: 2, o: 1}

function numberOfChar(prameter) {
    let object = {};
    let arrayFromPrameter = prameter.split("");
    for (let i = 0; i < arrayFromPrameter.length; i++){
        let sum = 1;
        for (let j = 1; j < arrayFromPrameter.length; j++){
            if (arrayFromPrameter[i] === arrayFromPrameter[j])
                sum += 1;
        }
        Object.defineProperty(object, arrayFromPrameter[i], {
            value: sum
        });
    }
    return object;
}
console.log(numberOfChar("hello"));

// 15. Write a function that sorts an array of numbers in ascending order.
// Input: [5, 3, 8, 1, 2]
// Output: [1, 2, 3, 5, 8]

// by using sort() method
let sortingArray = (arr) => arr.sort();
console.log(sortingArray([5, 3, 8, 1, 2]));

// by using sorting algorithms like selection sort

function sortingArrayTwo(arr) {
    for (let i = 0; i < arr.length - 1; i++)
    {
        let iMin = i;
        for (let j = i + 1; j < arr.length; j++)
        {
            if (arr[j] < arr[iMin])
                iMin = j;
        }
        if (iMin != i)
            [arr[iMin], arr[i]] = [arr[i], arr[iMin]];
    }
    return arr;
}
console.log(sortingArrayTwo([5, 6, 3, 4, 2]));

// 16. Write a function to check if a given string is an anagram of another string (i.e., contains
// the same characters in a different order).
// Input: "listen", "silent"
// Output: true

function sameChar(stringOne, stringTwo) {
    let largest, lowest;
    if (stringOne.length >= stringTwo.length) {
        largest = stringOne;
        lowest = stringTwo;
    } else {
        lowest = stringOne;
        largest = stringTwo;
    }
    let haveSameChar = true;
    for (let i = 0; i < lowest.length; i++){
        if (!largest.includes(lowest[i]))
            haveSameChar = false;
    }
    return haveSameChar;
}
console.log(sameChar("listen", "silent"));

// 17. Write a function that removes all falsy values (`false`, `null`, `0`, `""`, `undefined`,
// and `NaN`) from an array.
// Input: [0, false, "Hello", "", null, undefined, NaN, 42]
// Output: ["Hello", 42]

function removeFalsyValues(prameter) {
    return prameter.map((el) => {
        if (el)
            return el;
        else
            return "";
    }).filter((el) => el !== "");
}
console.log(removeFalsyValues([0, false, "Hello", "", null, undefined, NaN, 42]));

// 18. Write a function that creates a car object with properties such as `model` and `year’
// and includes a method to display the car's details.
// Input: Toyota, 2020
// Output: "Model: Toyota, Year: 2020"

function createObject(m, y) {
    let obj = {};
    Object.defineProperties(obj, {
        Model: {
            value: m
        },
        Year: {
            value: y
        }
    })
    obj.displayData = () => `"Model: ${obj.Model}, Year: ${obj.Year}"`;
    return obj.displayData();
}
console.log(createObject("toyota", 2020));

// 19. Write a function that checks if a given object contains a specific property.
// Input: {name: "Alice", age: 25}, "name"
// Output: true
// Input: {name: "Alice", age: 25}, "address"
// Output: false

function containsSpecificPfop(obj,prop) {
    if (obj[prop])
        return true;
    else
        return false;
}
console.log(containsSpecificPfop({ name: "Alice", age: 25 }, "address"));

// 20. Write a function to count the number of vowels (a, e, i, o, u) in a string, regardless of
// case.
// Input: "Hello World"
// Output: 3

function numberOfVowels(string) {
    let arr = ["a", "e", "i", "o", "u"], sum = 0;
    for (let i = 0; i < string.length; i++){
        if (arr.includes(string[i]))
            sum += 1;
    }
    return sum;
}
console.log(numberOfVowels("Hello World"));

// 21. Write a function that splits a string into an array of words based on spaces.
// Input: "The quick brown fox"
// Output: ["The", "quick", "brown", "fox"]

function splitString(string) {
    return string.split(" ");
}
console.log(splitString("The quick brown fox"));

// 22. Write a function that performs a mathematical operation (`+`, `-`, `*`, `/`) on two
// numbers.
// Input: 5, 3, "+"
// Output: 8
// Input: 5, 3, "%"
// Output: "Invalid operator"

function mathematicalOperations(numberOne, numberTwo, operation) {
    let result;
    switch (operation) {
        case '+':
            result = numberOne + numberTwo;
            break;
        case '-':
            result = numberOne - numberTwo;
            break;
        case '*':
            result = numberOne * numberTwo;
            break;
        case '/':
            result = numberOne / numberTwo;
            break;
        default:
            result = "invalid operation";
    }
    return result;
}
console.log(mathematicalOperations(5, 3, '%'));
