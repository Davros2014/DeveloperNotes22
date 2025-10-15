### Icon Issues

You might notice a few unexpected changes to your icons during the migration. As we have been streamlining the css, we have noticed that many of the css classes are not aligned to the design system. 

As an example, the css class name for the cancel or close icon should be in sentence case ie Cancel or Close and be prefixed with the "Icon" class - "Icon Close", These are defined in the design system > layout > icons. 

*You can copy the class name to the clipboard by clicking on their respective icon name.*

Currently we have classes defined in the css that have been added to suit the code instead of vice versa such as the following: 

	.Icon.Close::before,
	.Icon.Cancel::before,
	.Icon.close::before,
	.Icon.cancel::before {
	  content: "\f00d";
	}

This is a simple example, for some we have multiple different variations. This should not be the case and as such will be redefined to the following;

	.Icon.Close::before,
	.Icon.Cancel::before {
	  content: "\f00d";
	}

In the interests of best practice and trying to make the code more manageable long term, please amend the class names in your applications. Thank you for your understanding :)



On another matter, I think the portal width seems a bit too narrow (at least on my screen). I think it has been set to 1440px and then there are further widths/margins applied to containers within that which make the actual width a percentage of that, in this case 1142.43px. Could we change this?


Webiny, staffbase & magnolia


