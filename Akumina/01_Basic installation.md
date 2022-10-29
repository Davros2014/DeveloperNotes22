Requires Node to be installed on your system

In your terminal cd into the folder you want to create your project in

1. Install Yoeman > npm install yo

2. Install  Akumina generator > npm install generator akumina 

3. Install  Akumina project > npx yo akumina

You'll be promted for the following: 
1. Project name
2. Client namespace 
3. Akumina version (ie 5.5)
4. Use React? Y/N
5. Widget name 
6. Widget Source path (ie src/js/widgets)
7. Use Typescript? Y/N

Project files will be generated for you

To correct the version of webpack needed use > npm uninstall  webpack-cli

And install version 3.3.12 > npm i webpack-cli@3.3.12

To start site > npm start

------------------------------------

### Environment and deployment steps

Define environment variables in the .env file

In the akumina.sitedeployer.config.json file: 


	// these deployment steps will be run if set to true and in the order it exists in this file
	{
	  "Options": {
	    "masterpage": false,
	    "js": false,
	    "css": false,
	    "lists": false,
	    "layouts": false,
	    "pages": false,
	    "controls": false,
	    "widgets": true, 
	    "groups": false,
	    "contentfiles": false,
	    "imagefiles": false,
	    "updatelists": false,
	    "homepage": false,
	    "fonts": false,
	    "virtualpages": false,
	    "cdnassets": false
	  },
	
	  "Args":  [
	    "version",
	    "envdir",
	    "assetdirectory",
	    "options",
	    "ml",
	    "langid",
	    "spdirectory",
	    "spurl",
	    "spuser",
	    "sppassword",
	    "clientid",
	    "clientsecret",
	    "azurestorageaccountname",
	    "azurestoragecontainer",
	    "azurestorageaccountkey",
	    "cdnprefix",
	    "multideployment",
	    "centralspurl"
	  ]
	}

If you make changes to the above run the follwoing afterwards > npm run deploy