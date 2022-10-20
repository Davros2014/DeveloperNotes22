In JavaScript, when you hear the term "loop", you probably think of using the various loop methods like [`for` loops](https://www.freecodecamp.org/news/javascript-for-loops/), [`forEach()`](https://www.freecodecamp.org/news/javascript-foreach-js-array-for-each-example/), `map()` and others.

But in the case of objects, unfortunately, these methods don't work because objects are not iterable.

This doesn't mean we can't loop through an object – but this means that we can't loop through an object directly the same way we do for an array:

	```let arr = [24, 33, 77];
	arr.forEach((val) => console.log(val)); // ✅✅✅
	
	for (val of arr) {
	  console.log(val); // ✅✅✅
	}
	
	let obj = { age: 12, name: "John Doe" };
	obj.forEach((val) => console.log(val)); // ❌❌❌
	
	for (val of obj) {
	  console.log(val); // ❌❌❌
	}```

In this article, You'll learn how you can loop through an object in JavaScript. There are two methods you can use - and one of them pre-dates the introduction of ES6.

## How to loop through an object in JavaScript with a `for …in` loop

Before ES6, we relied on the `for...in` method whenever we wanted to loop through an object.

The `for...in` loop iterates through properties in the prototype chain. This means that we need to check if the property belongs to the object using `hasOwnProperty` whenever we loop through an object with the `for…in` loop:

	const population = {  
	  male: 4,  
	  female: 93,  
	  others: 10  
	};  

// Iterate through the object  
for (const key in population) {  
  if (population.hasOwnProperty(key)) {  
    console.log(`${key}: ${population[key]}`);  
  }  
}

To avoid the stress and difficulty of looping and to use the `hasOwnProperty` method, ES6 and ES8 introduced object static methods. These convert object properties to arrays, allowing us to use array methods directly.

## How to loop through an object in JavaScript with object static methods

An object is made up of properties that have key-value pairs, that is each property always has a corresponding value.

Object static methods let us extract either `keys()`, `values()`, or both keys and values as `entries()` in an array, allowing us to have as much flexibility over them as we do with actual arrays.

We have three object static methods, which are:

-   `Object.keys()`
    
-   `Object.values()`
    
-   `Object.entries()`
    

### How to loop through an object in JavaScript with the `Object.keys()` method

The `Object.keys()` method was introduced in ES6. It takes the object we want to loop over as an argument and returns an array containing all property names (also known as keys).

const population = {  
  male: 4,  
  female: 93,  
  others: 10  
};  
​  
let genders = Object.keys(population);  
​  
console.log(genders); // ["male","female","others"]

This now gives us the advantage of applying any array looping method to iterate through the array and retrieve the value of each property:

let genders = Object.keys(population);  
​  
genders.forEach((gender) => console.log(gender));

This will return:

"male"  
"female"  
"others"

We can also use the key to get the value using bracket notation such as `population[gender]` as seen below:

genders.forEach((gender) => {  
  console.log(`There are ${population[gender]} ${gender}`);  
})

This will return:

"There are 4 male"  
"There are 93 female"  
"There are 10 others"

Before we move on, let's use this method to sum all the population by looping through so we know the total population:

const population = {  
  male: 4,  
  female: 93,  
  others: 10  
};  
​  
let totalPopulation = 0;  
let genders = Object.keys(population);  
​  
genders.forEach((gender) => {  
  totalPopulation += population[gender];  
});  
​  
console.log(totalPopulation); // 107

### How to loop through an object in JavaScript with the `Object.values()` method

The `Object.values()` method is very similar to the `Object.keys()` method and was introduced in ES8. This method takes the Object we want to loop over as an argument and returns an array containing all key values.

const population = {  
  male: 4,  
  female: 93,  
  others: 10  
};  
​  
let numbers = Object.values(population);  
​  
console.log(numbers); // [4,93,10]

This now gives us the advantage of applying any array looping method to iterate through the array and retrieve the `value` of each property:

let numbers = Object.values(population);  
​  
numbers.forEach((number) => console.log(number));

This will return:

4  
93  
10

We can efficiently perform the total calculation since we can loop through directly:

let totalPopulation = 0;  
let numbers = Object.values(population);  
​  
numbers.forEach((number) => {  
  totalPopulation += number;  
});  
​  
console.log(totalPopulation); // 107

### How to loop through an object in JavaScript with the Object.entries() method

The `Object.entries()` method was also introduced with ES8. In the basic sense, what it does is that it outputs an array of arrays, whereby each inner array has two elements which are the property and the value.

const population = {  
  male: 4,  
  female: 93,  
  others: 10  
};  
​  
let populationArr = Object.entries(population);  
​  
console.log(populationArr);

This outputs:

[  
  ['male', 4]  
  ['female', 93]  
  ['others', 10]  
]

This returns an array of arrays, with each inner array having the `[key, value]`. You can use any array method to loop through:

for (array of populationArr){  
  console.log(array);  
}  
​  
// Output:  
// ['male', 4]  
// ['female', 93]  
// ['others', 10]

We could decide to [destructure the array](https://www.freecodecamp.org/news/destructuring-patterns-javascript-arrays-and-objects/), so we get the `key` and value:

for ([key, value] of populationArr){  
  console.log(key);  
} 

You can learn more about how to [loop through arrays in this article](https://www.freecodecamp.org/news/how-to-loop-through-an-array-in-javascript-js-iterate-tutorial/).