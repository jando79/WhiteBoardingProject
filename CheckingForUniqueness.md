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

