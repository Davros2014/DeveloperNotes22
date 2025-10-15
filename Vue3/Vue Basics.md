

#### v-model || @model

Binds data from input to a variable of the same name

	<div>  
	  <input v-model="greeting"/>`  
	  {{ hello world }}  
	</div>

### IF

	data: function() {  
	  return {  
	      isVisible: false;  
	      greeting: "hello world"  
	  }  
	}

#### v-if 

Removes element from DOM if value is falsey

	<div v-if="isVisible" /div>

#### v-else-if & v-else 

Will show v-if if "isVisible" is true, if not and "isAlsoVisible" is true it will display the div with v-else-if (there can be as many as required of these). Lstly will display the element with v-else

	<div v-if="isVisible" /div>  
	<div v-else-if="isAlsoVisible" /div>  
	<div v-else class=last box/div>

#### v-show 

If the visibility status shows a lot, it might be best to use v-show, it does not remove an element from the DOM but adds 'display: none' to the element to hide.
### v-cloak

Will hide elements before the page is loaded - should be added to main app. When page is loaded v-cloak is removed fropm the #app element

	<style>  
	  [v-cloak] {  
	    display: none;  
	  }  
	</style>  
	​  
	​  
	<div id="app v-cloak >  
	  // app stuff here  
	</div>  
	​

### v-on

For events - in this case an onclick event. Sets isVisible to true on clicking the button.

	<button v-on:click="isVisible = true"> Show Box </style>

Sets isVisible to false on click.

	<button v-on:click="isVisible = false"> Show Box </style>

Or toggle by setting the value to the opposite of current value.

	<button v-on:click="isVisible = !isVisible"> Show Box </style>

Shorthand for this event handler is to use @click instead of v-on:click

	<button @click="isVisible = !isVisible"> Show Box </style>

A method can be passed to the click event as such and create method in the data object under methods object

	<button @click="toggleBox"> Show Box </style>  
	​  
	data: function() {  
	  return {  
	      // other variables  
	  }  
	},   
	methods: {  
	  toggleBox() {  
	    this.isVisible = !this.isVisible;  
	  }  
	} 

### v-bind or : (for binding to html attributes)

Will bind data from state to be passed down to child-component (aside: @submit.prevent = adds preventDefault() to function on submit)

	<form @submit.prevent="handleSubmit">   
	  // other elements  
	  <custom-input type="email" v-bind:label="emailLabel">  
	  <a :href="url">Link to website</a>  
	    
	</form>  


	
	data: function() {  
	  return {  
	      emailLabel: email  
	      url: "https://www.somewebsite.co.uk"  
	  }  
	}

### @keyup

The following will log "greetings" to the console on pressigng the enter key

	<input @keyup.enter="greetings">  
	​  
	data: function() {  
	  return {  
	      // other variables  
	  }  
	},   
	methods: {  
	  // other functions  
	  greet() {  
	    console.log(this.greeting) // logs "greetings"  
	  }  
	} 

The following will call the function **greet** with whatever is passed as an argument (**.enter being a modifier to the keyup event listener**)

	<input @keyup.enter=(greet(greeting + !!!!!))>  
	​  
	data: function() {  
	  return {  
	      // other variables  
	  }  
	},   
	methods: {  
	  // other functions  
	  greet(greeting) {  
		    console.log(greeting) // logs "greetings!!!!!" Note: "this" not used as the argument comes from the value passed to the function itself  
	  }  
	} 

### v-for

	​  
	data: function() {  
	  return {  
	      books: [  
	        {title: 'title1', author: 'author1'},  
	        {title: 'title2', author: 'author2'},  
	        {title: 'title3', author: 'author3'},  
	      ]  
	  }  
	},    
	​  
	​  
	<ul >   
	  <li v-for:book in books>  
	    <h3>{{book.title}}</h3>   
	    <p>{{book.author}}</p>  
	  </li>  
	</ul>