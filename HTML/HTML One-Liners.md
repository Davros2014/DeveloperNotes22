## #1. Tooltip

<body><p>  
<abbr title="World Health Organization">WHO</abbr> was founded in 1948.  
</p>  
<p title="Free Web tutorials">W3Schools</p></body>

No CSS or JavaScript is needed for adding a simple tooltip to your HTML elements.

With the `title` attribute, you can easily add a tooltip to provide extra information to your users.

![img](https://miro.medium.com/max/60/1*L4mseTRzNIIzuZe9Xt5lJw.png?q=20)

![img](https://miro.medium.com/max/464/1*L4mseTRzNIIzuZe9Xt5lJw.png)

Demo of the code snippet above.

## #2. Download

<a href="/images/myw3schoolsimage.jpg" download>

The `download` attribute is incredibly helpful when you want your users to download the link instead of navigating to the file.

Moreover, you can also set the filename of the file your user will download.

<a href="link/to/your/file" download="filename">Download link</a>

## #3. Word Break Opportunity

<p>This is a veryveryveryveryveryveryveryveryveryveryveryveryveryveryveryveryveryvery<wbr>longwordthatwillbreakatspecific<wbr>placeswhenthebrowserwindowisresized.</p>

Nobody likes when HTML breaks words where it’s not supposed to.

Using `<wbr>` , you can easily the points(opportunities) where it is okay to break words.

This is useful when the word is too long and there’s a good chance that the browser might break it at the incorrect place.

## #4. Text direction

<p dir="auto">This text is following dir=auto</p>

With `dir=”auto”` , the browser will change the text alignment as per the language of the content.

This is incredibly useful when you are dealing with languages that don’t follow the left to right like English.

A potential place to use this attribute is in social media chat apps.

## #5. Basic Accordion

<details>  
  <summary>Epcot Center</summary>  
  <p>Epcot is a theme park at Walt Disney World Resort featuring exciting attractions, international pavilions, award-winning fireworks and seasonal special events.</p>  
</details>

You can create a very basic yet easy accordion by using the `details` and `summary` semantic elements.

![img](https://miro.medium.com/freeze/max/60/1*wkHFCQAOJAJwkzQOBiKr0Q.gif?q=20)

![img](https://miro.medium.com/max/700/1*wkHFCQAOJAJwkzQOBiKr0Q.gif)

Demo of the code snippet above. Source: Author.

Wrap your accordion element with `details` element and for the title use the `summary` element. Lastly, use the `p` paragraph element to write the main content of the accordion.

## #6. Content Editable

<p contenteditable='true'>This is a paragraph. Click the button to make me editable.</p>

You can make any content editable by setting the `contenteditable` attribute to true.

It doesn’t matter if it’s a `div` or a `p` , it will become editable.

Moreover, you can also use the [isContentEditable](https://www.w3schools.com/jsref/prop_html_iscontenteditable.asp) property to find whether a certain element is editable or not.

## #7. Add Captions

<video width="320" height="240" controls>  
  <source src="forrest_gump.mp4" type="video/mp4">  
  <source src="forrest_gump.ogg" type="video/ogg">  
  <track src="fgsubtitles_en.vtt" kind="subtitles" srclang="en" label="English">  
  <track src="fgsubtitles_no.vtt" kind="subtitles" srclang="no" label="Norwegian">  
</video>

With just HTML, you can add captions to your video files using the `<track>` element.

Use the `src` attribute to point to the subtitles file and use the `srclang` attribute to set the language.

## #8. Lazy loading

<img src="/w3images/wedding.jpg" alt="Wedding" style="width:100%">  
<img src="/w3images/rocks.jpg" alt="Rocks" style="width:100%">  
​  
<!-- off-screen images -->  
<img src="/w3images/paris.jpg" alt="Paris" style="width:100%" loading="lazy">  
<img src="/w3images/nature.jpg" alt="Nature" style="width:100%" loading="lazy">  
<img src="/w3images/underwater.jpg" alt="Underwater" style="width:100%" loading="lazy">  
<img src="/w3images/ocean.jpg" alt="Ocean" style="width:100%" loading="lazy">  
<img src="/w3images/mountainskies.jpg" alt="Mountains" style="width:100%" loading="lazy">

You can load images on-demand(also called lazy loading) by setting the `loading` attribute to ‘lazy’.

This is a simple but very effective optimization technique that loads only the section that is visible to the user and the other images are loaded later, as per the user’s need.

## #9. Base URL

<head>  
  <base href="https://www.w3schools.com/" target="_blank">  
</head>  
​  
<body>  
<img src="images/stickman.gif" width="24" height="39" alt="Stickman">  
<a href="tags/tag_base.asp">HTML base Tag</a>  
</body>

If you make calls to a common domain various times on your website, you can use the `<base>` element to set a base URL as shown in the code snippet provided above.

Now the actual value of `src` in the image element is “[https://www.w3schools.com/images/stickman.gif](https://www.w3schools.com/images/stickman.gif)”.

It is a very common practice to set a base URL if you have used libraries like [Axios](https://axios-http.com/).

## #10. Controlling Context Menu and Paste

<input type="text" onpaste="return false" value="Paste something in here"><div oncontextmenu="myFunction()" contextmenu="mymenu">

You can listen to events like when they use right-clicks or try to paste content and handle these events with `oncontextmenu` and `onpaste` attributes.

If you don’t want users to be able to paste onto some field like password, you can write `onpaste=”return false”` on that input field and users won’t be able to paste there.

Similarly, `oncontextmenu` fires whenever the user right-clicks on that element.

## #11. Spellcheck

<p contenteditable="true" spellcheck="true">This is a praggagraph. It is editable. Try to change the text.</p>

The `spellcheck` attribute, when set to true, tells the browser that the user input in this element has to be checked for grammar and spelling mistakes.

It is a handy attribute that facilitates users to write correct and error-free content.

## Final thoughts…

While HTML lays out the structure of data, CSS styles it and makes it presentable.

However, HTML is much more capable than just setting up the structure of data.

With these powerful one-liner attributes, you can do much more directly from your HTML file.

If you enjoyed reading this article, consider becoming using [my referral link](https://medium.com/@anuragkanoria/membership) so you get unlimited access to my blogs as well as blogs from other authors by clicking [here](https://medium.com/@anuragkanoria/membership).

If you are using Chrome browser, feel free to check out my recent blog on Chrome extensions that I wish I knew earlier.