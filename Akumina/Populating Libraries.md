Create an Upload file in your sitedefinitions folder

> build > sitedefinition > UploadFiles

The UploadFiles folder should contain a folder for each document or media library you wish to populate. Before running this, ensure that you already have a library created within your site content folders

eg > build > sitedefinition > UploadFiles > Documents > Tutuorials

In akumina.sitedeployer.config.json under the "Options" object, add "uploadfiles": true

	{
	"Options": {
		... previous code, 
	    "uploadfiles": true
	  },
	}

To deploy changes, run > npm run deploy 

Confirm deployment of your files by navigating to your site and opening site contents (nav bar top-left)

In this case you should see a Documents folder under the content tab