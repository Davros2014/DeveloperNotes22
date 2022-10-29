Under build > branding > css

Add required CSS to the file as needed

In the akumina.sitedeployer.config.json file, under the "Options" object, change the CSS value to true.

Then in your terminal run > npm run deploy

*Important*: Then bind the CSS file to your Akumina page

Navigate to your site (aspx page)

Open the debug panel (green button at page center-bottom)

Then click the debug panel button (second left)

> Click the Modern tab at the bottom of the left-hand sidebar
> 	1. Click rthe Toggle Command Bar checkbox
> 	2. Close the debug modal
> 	3. Now click the Edit button that should have appeared top right on the page and scroll to the bottom of the App page details panel  
> 	4. Under the field "Comma delimited list of CSS...", add the path to your CSS files
> 	5. Click the save button (top left of the panel)
> 	6. Refresh page to see changes

