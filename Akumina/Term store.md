Add term sets using the terms.xml folder in the Taxonomy folder 

In akumina.sitedeployer.config.json under the "Options" object add "addtermsets": true

	{
	"Options": {
		... previous code, 
	    "addtermsets": true
	  },
	}

To deploy term sets, run > npm run deploy 

To confirm deployment of your term sets by navigating to your site and opening site settings
Term stores are managed in the term store management option within site administration

>Site settings > Site Administration > Term Store Management

Your term sets will be displayed within the site collection folder (side-bar left-bottom) under Resources