**Fontawesome free - CSS and webfonts usage**
The all.min.css file that we call in the global_head.vm file located here /internal/system/vm/custom/ makes use of font files found in the webfonts folder. 

Given the CSS @fontface styles use relative paths to this folder, the exception has been made to our usual file structure to keep the webfonts folder in situ here instead of moving it to the fonts folder as would be the norm. 