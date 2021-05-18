# Zuri-Algorithm-Test
An algorithm test that tests our javascript knowledge
1. Write a function named "convertFahrToCelsius" that takes a single parameter and converts it to celsius.

Note:

- Round up your answers to 4 decimal places (hint: use the toFixed method)
- C = (F - 32) x 5/9; (e.g 0deg F = -17.7778 deg C)
- if the parameter passed is not a number or a string that can be converted to a valid number, return a string with the format below:
    `${parameter} is not a valid number but a/an ${parameter's type}.`
You can use the following cases as guides:

- convertFahrToCelsius(0) should return `-17.7778`
- convertFahrToCelsius("0") should return `-17.7778`
- convertFahrToCelsius([1,2,3]) should return `[1,2,3] is not a valid number but a/an array.`
- convertFahrToCelsius({temp: 0}) should return `{temp: 0} is not a valid number but a/an object.`
 
 
 
Answer 1 

 let convertFahrToCelsius = (fahr) => {
  // checking if the fahr is a valid input
  if (isNaN(Number(fahr))){
    // fahr is not a valid input
    return `${JSON.stringify(fahr)} is not a valid number but a/an ${Array.isArray(fahr) ? "array": "object"}.`
  } else {
    // fahr is a valid input
    let c = (fahr - 32) * (5/9)
    return Number(c.toFixed(4));
  }
}  //end of function

2. Write a function named "checkYuGiOh" that takes a number, n, as an argument, creates an array of numbers from 1 to n and replaces multiples of 2, 3, and 5 with "yu", "gi" and "oh", then returns the resulting array.

Note:

- for numbers that have multiple factors, use hyphens as separators
e.g 10 === "yu-oh", 30 === "yu-gi-oh"
- perform checks on your input and return `invalid parameter: ${parameter}` if an invalid parameter - i.e. a string that can't be converted to a number or another data type - is passed. 
Use the following cases as guides:

- checkYuGiOh(10) should return [1, "yu", "gi", "yu", "oh", "yu-gi", 7, "yu", "gi", "yu-oh"]
- checkYuGiOh("5") should return [1, "yu", "gi", "yu", "oh"]
- checkYuGiOh("fizzbuzz is meh") should return `invalid parameter: "fizzbuzz is meh"`

Answer
let checkYuGiOh = (n) => {
  // Checking for invalid parameter
  if ( isNaN(Number(n)) ) {
    // n is not a number, hence return invalid parameter
    return `invalid parameter: ${n}`
  } //end of if function
  // helper function
  let getYuGiOh = (number) => {
    let answer = "";
    if ( number % 2 === 0){
      /* 2 is a multiple of number, that is 2 divides number without remainder and append 'yu' to answer */
      answer +="yu";
    } //end of if statement
    if ( number % 3 === 0) {
      /* 3 is a multiple of number, that is 3 divides number without remainder and append 'gi' to answer */
      /* if answer is an empty string just add 'gi' otherwise add '-' before 'gi' */
      answer = ( answer)? answer+"-"+"gi" : "gi";
    } // end of if statement
    if ( number % 5 === 0) {
      /* 5 is a multiple of number, that is 5 divides number without remainder and append 'oh' to answer. Also if answe is an empty string, add 'gi' otherwise add '-' before 'gi' */
      answer = ( answer ) ? answer+"-"+"oh" : "oh";
    } //end of if statement
    /* finanlly, if answer is still empty, because number is not a multiple of 2,3, and 5 return number */
    return (answer) ? answer : number; // return number if answer is blank
  } //end of getYuGiOh

  let result_Arr = [] // This will create a result array
  let processed_n = parseInt(n)  // This ensures n is an integer, because iteration requires integers
  for (let number = 1; number <= processed_n; number++) {
    /* Push the output of the getYuGiOh ( helper function defined earlier) to result array ('result_Arr') */
    result_Arr.push( getYuGiOh(number) )
  } // This is the end of for loop
  return result_Arr // This returns the result array
} // This is the end of the checkYuGiOh
