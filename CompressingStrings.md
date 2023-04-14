Write an algorithm that takes a string with repeated characters and compresses them, using a number to show how many times the repeated character has been compressed. For instance, aaa would be written as 3a. Solve the problem with and without recursion.

Example
Input: "aaabccdddda"

Output: "3ab2c4da"
=======================================================================================================================

Without Recursion:

function compress(input) { 
  let result = ""; 
  let counter = 1; 
  for (let i = 0; i < input.length; i++) { 
    if (input[i] === input[i + 1]) { 
      counter++; 
    } else { 
      if(counter === 1){ 
        counter = ""; result += counter + input[i]; counter = 1; 
      } else {
        result += counter + input[i];
        counter = 1;
      }
    }
  }
return result;

}


With Recursion:

function compressWithRecursion(input) { 
  if (input.length === 0) {
    return ""; 
  }
  let count = 1; 
  let i = 1;   
  while (i < input.length && input[i] === input[i - 1]) { 
  count++; i++; 
  } if(count === 1) { 
    count = ""; 
    return count + input[i - 1] + compressWithRecursion(input.slice(i));
  }
  return count + input[i - 1] + compressWithRecursion(input.slice(i)); 
}