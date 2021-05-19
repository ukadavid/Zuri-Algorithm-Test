# Zuri-Algorithm-Test

Please this is the link to my repository: https://github.com/ukadavid/Zuri-Algorithm-Test

I'm so sorry, i made a mistake to upload it as a github page. I put in a lot of work to this. 

Thank you for your understanding

 Below is also the answers to the problems.
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





Answer 2


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
