A closure is a function that makes use of variables defined in an outer function that has previously returned

	eg//  
	​  
	function outer () {  
	  var start = "closures are"  
	    return function inner () {  
	      return start + "awesome"  
	    }  
	}  
	​  
	outer()(); > returns "closures are awesome"  
	​  
	eg//  
	​  
	function outer (a) {  
	  return function inner (b) {  
	    // the inner function is making use of the varibale "a"  
	    // which was defined in an outer function called "outer"  
	    // by the time the einner function is called the outer function has returned  
	    // this function called "inner" is a closure  
	    return a + b;  
	  }  
	}  
	​  
	outer(5)(10) > returns 15  
	​  
	eg/  
	    
	  function outerFn () {  
	    var data = "something from outerFn"  
	    var fact = "Remember me!"  
	    return function innerFn () {  
	      debugger  
	      return fact;  
	    }  
	}  
	​  
	outerFn()() > returns "Remember Me" but not "something from outerFn"  
	​  
	COUNT EXAMPLE - PRIVATE VARIABLE  
	​  
	funciton count() {  
	  var count = 0;  
	  funtion inner () {  
	    count++  
	    return count;  
	  }  
	}  
	count() > returns 1 first time  
	count() > returns 2 second time and so on  
	​  
	var counter2 = count();  
	counter2(); = 1 returns 1 first time  
	counter(); = 2 > returns 2 second time and so on  
	​  
	// the value of the 'count' variable is not affected by counter2  
	// run count() again  
	count() > returns 3   
	​  
	calling count = ReferenceError: count is not defined - because it is private!  
	​