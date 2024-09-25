#### Windows 10+

1.  Right-click **This PC** and select **Properties**. 
2.  Go to the **Advanced System Properties** tab.  
4. This will open Local Admin - you will need to open Local Admin Manager prior to this step and make sure you have copied down your password (take a picture - copy/paste doesn't work). 
5. Username  `.\LocalAdmin`
6. Then click **Environment variables** and add **Variable** name as JAVA_HOME and the **Value** to `C:\Program Files\Java\jdk-10.0.xx`


#####  Download Magnolia - [magnolia-community-demo-webapp-6.2.30-tomcat-bundle.zip](https://nexus.magnolia-cms.com/service/local/repositories/magnolia.public.releases/content/info/magnolia/bundle/magnolia-community-demo-webapp/6.2.30/magnolia-community-demo-webapp-6.2.30-tomcat-bundle.zip)


1.  Extract to `C:\Users\<username>`

2.  Open a command prompt and navigate to the Magnolia installation directory.  
    To do this, type `cd C:\Users\<username>\magnolia-x.y\apache-tomcat\bin`

`cd C:\Users\ArajarDW\magnolia\magnolia-6.2.30\apache-tomcat-9.0.73\bin`
   
3.  Type `magnolia_control.bat start` and press ENTER.  
    Magnolia reports startup information in a new Tomcat window. If startup fails, look for the reason in the report. In a successful startup the last line reads: `INFO: Server startup in 12345 ms`

**STOP Magnolia** 
To stop Magnolia, type `CTRL + C`, then `./magnolia_control.bat stop` and press ENTER.


### Web update

To install Magnolia:

1.  Open a browser and go to [`http://localhost:8080`](http://localhost:8080/).
    
2.  Click **Run the Web update on the author instance**, then **Start installation**.
    
3.  Click **Run the Web update on the public instance**, then **Start installation**.


### Login

Go to [`http://localhost:8080/magnoliaAuthor`](http://localhost:8080/magnoliaAuthor) and sign in as:

-   Username: `superuser`  
-   Password: `superuser`


##### **Magnolia Core Module**  6.2.30
-   Please set the config:/server/defaultBaseUrl property to a full URL to be used when generating absolute URLs for external systems.

### Cache Browser

https://demo.magnolia-cms.com/.magnolia/admincentral#app:cacheTools:browser

Icons - font-awesome

Bell: class="fa-regular fa-bell"

Arrow-left: class="fa fa-angle-left fa-2xl"

Arrow-right: class="fa fa-angle-right fa-2xl"

Bookmark: class="fa-regular fa-bookmark"

Search: class="fa-sharp fa-regular fa-magnifying-glass"



### Nav text


[EMEA Portal](https://akemea.intranet.basf.com/)
    
-   About Us
    
-   Sub Regions
    
-   [Regional Service Coordination Teams](https://emea.basf.net/portal/load/fid1182423/EMEACoordinationTeams.pdf)
    
-   Action Areas
    
-   News & Info


## Quick Links

-   [](https://service4you.intranet.basf.com/)[Service4You!](https://service4you.intranet.basf.com/)
-   [](https://kiosk.basf.net/)[HRkiosk](https://kiosk.basf.net/)
-   [](https://translator.basf.com/translate)[BASF Translator](https://translator.basf.com/translate)
-   [](https://brandportal.basf.com/global/de.html)[BASF Brand Portal](https://brandportal.basf.com/global/de.html)
-   [](https://service4you.intranet.basf.com/esc?id=basf_printing_portal)[Global Printing Portal](https://service4you.intranet.basf.com/esc?id=basf_printing_portal)
-   [](https://akemea.intranet.basf.com/)[IS Service Desk](https://akemea.intranet.basf.com/)


Hi Antonio, 

Sorry for taking a while to get back to you, I was caught up on other matters.

Staffbase has a fairly broad range of APIs available to it, you can view them here; 

https://developers.staffbase.com/api/

Microsoft integration comes out of the box and has a number of configurable widgets - https://support.staffbase.com/hc/en-us/articles/360021042060-Configuring-the-Microsoft-365-Teams-Overview-Widget
but there are connectors for certain tools and systems from Microsoft available also: https://learn.microsoft.com/en-us/connectors/staffbase/

Do you remember more specifically the issue that Nils had with Staffbase and API's?