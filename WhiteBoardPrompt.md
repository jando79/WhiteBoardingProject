<a href="https://codeshare.io/pqNVeX">Code Share Link</a>

array duping

algorithm removes duplicates. without recursion and with recursion. lastly, using a filter

input[7,9, "hi", 12, "hi", 7, 53]

output[7, 9, "hi", 12, 53]

create input array
create new [] tp store elements that arent dupes
loop through the input and check whether characters are duplicates if not dupklicates push to new array



function dedupeArray(inputArray) {
let newArray = [];
for (let i = 0; i < inputArray.length; i++) {
if (!newArray.includes(inputArray[i])) {
	newArray.Push(inputArray[i]);
}
}
return newArray;
}

with recursion:

function usingRecursion(input, result = []) {
	if (input.length === 0) {
  return result;
  }
  let newIndex = input[0];
  if (!result.includes(newIndex)) {
  	result.push(newIndex);
  }
  return usingRecursion(input.slice(1), result);
  }
  
  with filter:
  
  function removeDuplicate(array) {
  return array.filter((item, index) => array.indexOf(item) === index);
  }