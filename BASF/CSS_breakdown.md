The list below follows the structure: HTML description - Element location - css selector

Application name - app page top right
```
 #Action_ApplicationName_Inner span
```

Application width - various locations
```
#Navigation_portal_function_grid {
	width: 1440px;
	margin: 0 auto;
}
```

Container_AppMain

```
#Container_AppMain {
  position: relative;
  overflow: hidden;
  margin-top: 1rem;
  background: white;
  padding: 1rem;
  margin-top: 0;
```


```
#CONT_dropdown ul li[id|="SEPARATOR"] {
	position: relative;
	margin: 0;
	white-space: nowrap;
	background: rgba(var(--whiteRGB), var(--opacity20));
	color: var(--white);
	text-align: center;
	border-top: 1px solid rgba(var(--whiteRGB), var(--opacity50));
	border-bottom: 1px solid rgba(var(--whiteRGB), var(--opacity50));
	font-weight: 900;
}
```

#App_title

```
#App_title {
	background-color: #d7d4d4;
	color: #000123;
	font-family: Arial;
	letter-spacing: 0.05rem;
	border-top-left-radius: 5px;
	border-top-right-radius: 5px;
}
```


Editfield_Standard {
	padding: 0.75rem 1.5rem;
	line-height: 2rem;
	font-size: 1.4rem;
	-webkit-appearance: none;
	transition: all .2s ease;
	margin-top: 0.5rem;
	background: #fff;
}

border: 1px solid var(--grey25);
box-shadow: none;
min-height: 35px;
height: 35px;
background: var(--white);




Editfield_Standard::placeholder {
	color: var(--grey25);
	max-width: 95%;
	text-overflow: ellipsis;
	white-space: nowrap;
	overflow: hidden;
	transition: color .2s ease-in;
}



const mySearchFunction = () => {

    // Declare variables

    console.log("clicked")

    let input, filter, ul, li, a, i;

    input = document.getElementById("IcnSearchField");

    filter = input.value.toUpperCase();

    ul = document.getElementById("Iconlink_section");

    li = ul.getElementsByClassName("col-3");

  

    // Loop through all list items, and hide those who don't match the search query

    for (i = 0; i < li.length; i++) {

        a = li[i].getElementsByTagName("a")[0];

        if (a.innerHTML.toUpperCase().indexOf(filter) > -1) {

            li[i].style.display = "";

        } else {

            li[i].style.display = "none";

        }

    }

}