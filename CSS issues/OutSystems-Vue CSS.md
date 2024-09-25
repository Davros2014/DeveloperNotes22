#### OutSystems vs Vue3 CSS styling issues
We have two systems (OutSystems and Vue3) and we want to be able future proof potential issues and conflicts down the line by utilising as much of the same styling (CSS files) as possible, with as little repetition as possible. 

The issues here are the following;

* OutSystems has it's own internal styling upon which it is tailored to meet BASF styling via the BASF_reactive theme
* In Vue3 we have no base styles as far as I am aware, other departments have used Tailwind for leveraging basic utility classes, upon which a mix of BASF_semanticUI components have been used (but this is now being deprecated) or utilising components built by the Atoms team (the current version (3) has just been released but doesn't have Vue support as yet but it is expected soon.)
* Which styles should we be following - is there a universal global theme available? There are many different ones but which should we be adhering to?

** Some aspects of the setup in OutSystems means that certain features will need to be replicated - icons are built into the framework, but use font-awesome classes which we can also tap into through an npm package in Vue3, so whilst this is somewhat a repetition, it is an easier fix than we face with more general styling. ** 

How can we resolve this? 

* Is there a way of utilising the same css files (without duplicating them) so that at the very least we can leverage the BASF_reactive theme - we probably need to resort to using utility classes from something like Tailwind as a base set up - but to have the global theme styles available to us. 
* Can we deviate from the overall style for apps made with app store and Vue3? This involves a bit more maintenance in general or at the very least more initial set up. 
* And in general is there an issue with us developing a different "look" for those apps developed within the app store. Still in keeping with styles within the whole BASF brand but just different from the styling for apps we develop in OutSystems?