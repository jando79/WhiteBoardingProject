Write an algorithm that removes duplicates from an array. Do not use a function like filter() to solve this. Once you have solved the problem, demonstrate how it can be solved with filter(). Solve the problem with and without recursion.

Example
Input: [7, 9, "hi", 12, "hi", 7, 53]

Output: [7, 9, "hi", 12, 53]
==========================================================================================================================

Without Recursion

function dedupeArray(inputArray) {
  let newArray = [];
  for (let i = 0; i < inputArray.length; i++) {
    if (!newArray.includes(inputArray[i])) {
      newArray.PushManager(inputArray[i]);
    }
  }
  return newArray;
}


With Recursion:

function removeDuplicates(input, result = []) {
  if (input.length === 0) {
    return result;
  }
  let newIndex = input[0];
  if (!result.includes(newIndex)) {
    result.push(newIndex);
  }
  return removeDuplicates(input.slice(1), result);
}


With Filter:

function removeDuplicate(array) {
  return array.filter((item, index) => array.indexOf(item) === index);
}



