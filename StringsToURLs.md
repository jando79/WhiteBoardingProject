URLs cannot have spaces. Instead, all spaces in a string are replaced with %20. Write an algorithm that replaces all spaces in a string with %20.

You may not use the replace() method or regular expressions to solve this problem. Solve the problem with and without recursion.

Example
Input: "Jasmine Ann Jones"

Output: "Jasmine%20Ann%20Jones"
==========================================================================================================================
Without Recursion:

function replace (input) {
  let result = "";
  for (let i = 0; i < input.length; i++) {
    if (input[i] === " ") {
      result += "%20";
    } else {
      result += input[i];
    }
  }
  return result;
}


With Recurssion:

function replace (usingRecursion) {
  if (usingRecursion.length === 0) {
    return "";
  }
  if (usingRecursion[0] === " ") {
    return "%20" + replace(usingRecursion.substring(1));
  }
  return usingRecursion[0] + replace(usingRecursion.substring(1));
}

