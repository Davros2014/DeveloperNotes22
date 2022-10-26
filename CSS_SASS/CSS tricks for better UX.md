10 CSS Tricks That Greatly Improve User

Experience: Spend 1 hour to learn, and enhance your web app forever.

### 1 - Clickable area  

Sometimes your button is small, which may cause users to not be able to click the button accurately. This phenomenon often occurs on mobile phones.

It can be very frustrating for users if they click too many times and don’t click the button they want, or click the wrong button.

So how to solve this problem? Some developers might say: make the button bigger.

But the sizes of elements in webpages are often fixed, we cannot easily adjust the size of an element. And if the button is too big, it feels weird.

A better solution is to increase the clickable area of the button without changing its original size. Specifically: we can use pseudo-elements to increase the clickable area of an element.

For example, here is a button:

	<button id="btn">btn</button>

Then we can add a pseudo-class for it:

	#btd:before {
	
		position: absolute; 
		top: -20px;  
		right: -20px; 
		bottom: -20px; left: -20px;
	
	}


### 2 - Smooth Scroll