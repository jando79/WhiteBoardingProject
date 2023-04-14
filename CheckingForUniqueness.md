Write an algorithm that determines whether all the elements in a string are unique. You may not convert the string into an array or use array methods to solve this problem. The algorithm should return a boolean.

Example
Input: "hello"

Output: false

Input: "copyright"

Output: true
==========================================================================================================================

Without Recursion:

function unique(input) {
for (let i = 0; i < input.length; i++) { 
    for (let x = i + 1; x < input.length; x++) {
        if (input[i] === input[x]) {
          return false;
        }
    }
  }
  return true;
}


With Recursion:

function withRecursion(input) { 
  if (input.length === 1) {
  return true;
  } 
  for (let i = 1; i < input.length; i++) {
    if (input[0] === input[i]) {       
      return false;
    }
}

return withRecursion(input.slice(1));
}

