
## React Fundamentals

### JSX Elements
---------------------------------

React applications are structured using a syntax called JSX. This is the syntax of a basic JSX element

	/*  
	JSX allows us to write in a syntax almost identical to plain HTML.  
	As a result, JSX is a powerful tool to structure our applications.  
	JSX uses all valid HTML tags (i.e. div/span, h1-h6, form/input, img, etc). */
	
	<div>Hello React!</div>
	
	/*  
	Note: this JSX would not be visible because it is needs to be rendered by our application using ReactDOM.render() 


JSX is the most common way to structure React applications, but JSX is not required for React

	/* JSX is a simpler way to use the function React.createElement() In other words, the following two lines in React are the same: */
	
	<div>Hello React!</div> // JSX syntax  
	React.createElement('div', null, 'Hello React!'); // createElement syntax

JSX is not understood by the browser. JSX needs to be compiled to plain JavaScript, which the browser can understand.

The most commonly used compiler for JSX is called Babel

	/*  
	When our project is built to run in the browser, our JSX will be converted by Babel into simple React.createElement() function calls From this...  
	*/  
	const greeting = <div>Hello React!</div>;
	
	/* ...into this: */ "use strict";
	
	const greeting = /*#__PURE__*/React.createElement("div", null, "Hello React!");


JSX differs from HTML in several important ways

	/*  
	We can write JSX like plain HTML, but it's actually made using JavaScript functions. Because JSX is JavaScript, not HTML, there are some differences:
	
	1) Some JSX attributes are named differently than HTML attributes. Why? Because some attribute words are reserved words in JavaScrip
	
	Also, because JSX is JavaScript, attributes that consist of multiple words are written in camelcase: */
	
	<div id="header">  
	<h1 className="title">Hello React!</h1>
	
	</div>
	
	/*  
	2) JSX elements that consist of only a single tag (i.e. input, img, br elements) must be closed with a trailing forward slash to be */
	
	<input type="email" /> // <input type="email"> is a syntax error
	
	/*  
	3) JSX elements that consists of an opening and closing tag (i.e. div, span, button element), must have both or be closed with a tra */
	
	<button>Click me</button> // <button> or </button> is a syntax error <button /> // empty, but also valid

Inline styles can be added to JSX elements using the style attribute  
Styles are updated within an object, not a set of double quotes, as with HTML Note that style property names must be also written in camelcase

	/*  
	Properties that accept pixel values (like width, height, padding, margin, etc), can use integers instead of strings. For example: fontSize: 22. Instead of: fontSize: "22px"  
	*/  
	<h1 style={{ color: "blue", fontSize: 22, padding: "0.5em 1em" }}>
	
	Hello React! </h1>;

JSX elements are JavaScript expressions and can be used as such  
JSX gives us the full power of JavaScript directly within our user interface

	/*  
	JSX elements are expressions (resolve to a value) and therefore can be assigned to plain JavaScript variables... */  
	const greeting = <div>Hello React!</div>;
	
	const isNewToReact = true;
	
	// ... or can be displayed conditionally function sayGreeting() {
	
	if (isNewToReact) {  
	// ... or returned from functions, etc. return greeting; // displays: Hello React!
	
	} else {  
	return <div>Hi again, React</div>;
	
	} }

JSX allows us to insert (or embed) simple JavaScript expressions using the curly braces syntax