#### 1 - GLOBAL CONTEXT

When "this" is not inside of a declared object

	console.log(this); // the value of "this" is the GLOBAL window
	
	function whatIsThis() {
	  return this;
	}
	
	whatIsThis() // the value of "this" is STILL the GLOBAL window - as it is not declared within an object
	
	
	function vaiableInThis() {
	  this.person = "elie"
	}
	vaiableInThis() - // the value of "this" is STILL the GLOBAL window
	console.log(person); // Elie - same as logging window.person

**> USING "STRICT MODE"**

	​  
	console.log("this") // window  
	​  
	function whatisThis() {  
	  return this  
	}  
	​  
	whatIsThis() // undefined - when strict mode is enabled  
	​    
	    
	function vaiableInThis() {  
	  this.person = "elie"  
	}  
	vaiableInThis() - // TypeError, can't set person on undefined  
	​  

#### 2 - IMPLICIT/OBJECT CONTEXT

When the keyword 'this IS inside of a declared object'

	// strict mode does NOT make a difference here
	
	var person = {
	  firstName: "Elie",
	  sayHi: function() {
	    return "Hi " + this.firstName;
	  },
	  determinContext: function() {
	    return this === person;
	  }
	}
	
	// NESTED OBJECTS
	
	var person = {
	  firstName: "Colt",
	  sayHi: function() {
	    return "Hi " + this.firstName;
	  },
	  determineContext: function() {
	  	return this === person;
		},
	  dog: {
			sayHello: function() {
	  		return "Hello " + this.firstName;
			},
	    determineContext: function() {
	  		return this === person;
			},
	}
	  
	person.determineContext // returns true
	person.sayHi // returns "Hi Colt"
	
	person.dog.sayHello // returns false - the parent object is the dog object
	person.dog.determineContext // returns false - the parent object is the dog object


#### 3 - EXPLICIT BINDING

Choose what we want the context of **"this"** to be using **CALL**, **APPLY** or **BIND**

These **3 methods** can **ONLY** be invoked by **functions**

**NAME OF METHOD PARAMETERS INVOKE IMMEDIATELY**

CALL thisArg, a, b, c, d, e... YES

---

APPLY thisArg, [a, b, c, d, e...] YES

---

BIND thisArg, a, b, c, d, e... NO


##### USING CALL


	var person = {
	  firstName: "Dave",
	  sayHi: function() {
	    return "Hi " + this.firstName;
	  },
	  determineContext: function() {
	  	return this === person;
		},
	  dog: {
			sayHello: function() {
	  		return "Hello " + this.firstName;
			},
	    determineContext: function() {
	  		return this === person;
			},
	}
	  
	person.dog.sayHello.call(person) // returns "Hello Dave"
	person.dog.determineContext.call(person) // returns true 
	
	// using call worked
	// Notice that we do NOT invoke sayHello or determinContext
	
> 	USING CALL IN THE WILD
	
	var dave = {
	  firstName: "Dave",
	  sayHi: function() {
	    return "Hi " + this.firstName;
	  }
	}
	// too much repetition below
	var elie = {
	  firstName: "Elie",
	  sayHi: function() {
	    return "Hi " + this.firstName;
	  }
	}
	dave.sayHi(); // Hi Dave
	elie.sayHi(); // Hi Elie
	
>	Using call
	
	var dave = {
	  firstName: "Dave",
	  sayHi: function() {
	    return "Hi " + this.firstName;
	  }
	}
	var elie = {
	  firstName: "Elie",
	}
	
	dave.sayHi.call(elie) // returns "Hi Elie"
	
>	improving the logic
	
	function sayHi() {
	  return "Hi " + this,firstName; 
	}
	
	var dave = {
	  firstName: "Dave",
	}
	var elie = {
	  firstName: "Elie",
	}
	
	sayHi.call(elie); // returns "Hi Elie";
	sayHi.call(dave); // returns "Hi Dave";
	
	
>	SELECTING DIVS ON A PAGE
	
	// you might weant to return all divs that have innerText of "SomeSpecificText"
	var divs  = document.getElementByTagName('div');
	
	divs.filter() // returns undefined as divs is not an array
	
	// convert our array-like object into an array
	// use the slice method, but instaed of the target of the clice (the keyowrd this) being that array, let's set the target of the keyword 'this' to be our divs array-like-object
	
	var divArray = [].slice.call(divs);
	// you might also see this as Array.prototype.slice.call(divs) - they do the same thing
	divArray.filter(val => {
	  return val.innerText === "SomeSpecificText";
	})


##### USING APPLY

	function sayHi() {
	  return "Hi " + this,firstName; 
	}
	var dave = {
	  firstName: "Dave",
	}
	var elie = {
	  firstName: "Elie",
	}
	
	sayHi.apply(elie); // returns "Hi Elie";
	sayHi.apply(colt); // returns "Hi Dave";
	
	// does pretty much the same as CALL until we add arguments
	
	function addNumbers(a, b, c, d) {
	  return this.firstName = just calculated " + (a+ b+ c+ d)"
	}
	var dave = {
	  firstName: "Dave",
	}
	var elie = {
	  firstName: "Elie",
	}

When a function does not accept an array as a parameter, apply will spread out the values in an array for us

	var nums = [5, 3, 8, 5, 6];
	
	Math.max(nums) // NaN
	
	Math.max.apply(this, nums) // returns 8
	
	function sumValues (a, b, c) {
		return a+ b + c;
	}
	var values = [4, 2, 1];
	
	sumValues(values); // "4, 1, 2undefinedundefined" - sees values as the first argument (a) and returns undefined for remaining arguments (b + c) as as far as it is concerned they dont exist 

##### USING BIND

The paramenters work like call, but bind returns a function with the context of "this" bound already!

	function addNumbers (a, b, c, d) {
		return this.firstName + " just calculated " + (a + b + c + d)
	}
	
	var elie = {
		firstName: "Elie"
	}
	
	var elieCalc - addNumbers.bind(elie, 1, 2, 3, 4) // returns a fucntion() {...}
	elieCalc() // Elie just calculated 10 
	// with bind we do not need to know all the arguments up front
	var elieCalc - addNumbers.bind(elie, 1, 2) // returns a fucntion() {...}
	elieCalc(3, 4) // Elie just calculated 10
	
	
	BIND IN THE WILD
	
	var dave = {
		firstName: "Dave",
	  sayHi: function() {
			setTimeout(function() {
	      console.log("Hi " + this.firstName.bind(this));
	    }, 1000);
	  }
	}
	// use bind as so 
	var colt = {
		...
			setTimeout(function() {
	      console.log("Hi " + this.firstName);
	    }.bind(this), 1000);
	  }
	}
	// returns "Hi Dave" after 1 second

#### 4 - NEW

We can set the context of the keyword "this" using the "new keyword - it does quite a bit more as well which will be covered in OOP