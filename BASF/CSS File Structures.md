-------

The principal CSS files for our design system can be found in the following folder location 

	\external\htmlroot\css\BASF_darkblue

Here you will find the following CSS files:

![[deprecationSupport.css]]

![[fckeditor.css]]

![[globalAnimations.css]]

![[globalHelpers.css]]

![[iconStyles.css]]

![[layout.css]]

![[print.css]]



** As a general rule, these are NOT to be touched unless permission is granted, if you need amendments or additional styles need to be included, please consult with David Arajarvi Parsons or any other person assigned with responsibility for this purpose. ** 

** The fckeditor.css, layout.css, and the print.css files are output in minified format from Intrexx (from the internal layout and user-defined style sheets) and should never be touched ** 

The above mentioned files are compiled by Intrexx and defined in the design app - BASF_darkblue as seen below

![[Design_app_Intrexx.png]]

Once you have opened the BASF_darkblue design application, navigate to the top left menu bar, click on icon on the far right side to access the source data of these CSS files as follows:

![[layout_styles_design_system.png]]

![[layout_editior_design_system.png]]

Within the design system there two ways that you can add layout styles - by accessing the file from the drop down menu > Edit layout styles (as seen above) or by accessing the control elements provided to us by Intrexx as seen below, both serve the same purpose and are output to the same destination file -  layout.css

![[Control_elements.png]]

The user-defined styles allows  
##### A brief breakdown on the content of the remaining files: 

* **deprecationSupport.css** - includes mainly styles that we ported from the old system, that hopefully will be phased out in the near future but currently we are dependent upon
* **globalAnimations.css** - as the name suggests, keyframe animations that have been extracted to their own file due to size
* **globalHelpers.css** - a collection of pre-defined size, colour, positional properties etc that can be easily implemented in your applications in the respective style tab of the element you are working with in Intrexx, alleviating the use of inline styles. Similar in essence to Bootstrap or Tailwind but we utilise these currently as they have been in place over a long time, but ideally should be phased out
* **iconsStyles.css** - font-awesome has become the icon tool of choice, we have a collection of pseudo classes available for stand-alone icons, for use in buttons, icons before and after text and other edge cases. We also use some BASF specific icon fonts. You can see more about the usage and what classes to adopt here: 

The above files are pre-loaded into Intrexx via a velocity file - customHeader.vm, which is located here: 

	\internal\system\vm\custom\custom_head.vm

** Again, this is purely for informational purposes and the file should not be touched unless you are authorised to do so. **

-----
As a general rule, don't add custom styles or inline styles - where possible, utilise the existing generic styles at your disposal - check the Design System Application for more in-depth information on how to use and where.  [Home - GB Portal (basf.net)](https://gbs-dev.basf.net/?rq_AppGuid=5C1A13C6D04388AE819D7AD35BAAF3A0038E2003&rq_TargetPageGuid=42CC18D764BAB27C1062EC3334A71C31035DA479&rq_RecId=2D31&rq_TemplateKey=7374616765)

---

