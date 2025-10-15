
## Table of contents:

-   Summary
-   Rules for Deployment 
-   Procedure of Deployment
-   Resources 
-   To Do's in this Article

## 1. Summary![](https://global-shared-services.basf.net/intranet/images/assets/007_wiki/icon_edit_inline.png "Edit this section")

 This article will cover the way how to prepare a deployment for a new version of an application

## 2. Rules for Deployment ![](https://global-shared-services.basf.net/intranet/images/assets/007_wiki/icon_edit_inline.png "Edit this section")

To create a "Deployment" "Work Item" in Azure DevOps, make sure that every "Work Item" you will link as "Predecessor" comes with a "Test Case" as a child and has the status "Done"

## 3. Procedure of Deployment![](https://global-shared-services.basf.net/intranet/images/assets/007_wiki/icon_edit_inline.png "Edit this section")

3.1.    Create a tag via SVN for your application, with ALL necessary files that are needed for the transport. --> [(Create SVN TAG)](https://global-shared-services.basf.net/intranet/default.asp?rq_AppGuid=4242993B67B3AD0B569B495176DE76C0604F62CA&rq_TargetPageGuid=18F7AA54A76A72F81B442BBC7F91457DB0A0C4D7&rq_RecId=3733323937&rq_Template=696E7465726E616C2F6C61796F75742F766D2F68746D6C2F4753534F5F6C69676874626C75652F6672616D65732F726F6F742E766D)

3.2.    You need to create a new Work item in “Azure DevOps” called “Deployment”

![[Pasted image 20221101171002.png]]

3.3    Fill the following fields:

-   1: Name of the work item = “[APPLICATION] deployment – [TAG]”
-   2: Azure DevOps Board Tags = [APPLICATION] & [APPLICATIONNUMBER]
-   3: Info/Description = Description of every step that is needed, to transport this TAG
-   4: Prerequisites and Dependencies = if your new TAG has new dependencies that are needed, please write 
        them into this field.
-   5: Configuration = Description of every step that is needed, to configurate the application properly, after the 
        transport is done.
-   6: Additional Notes = If there are some information’s that are not suitable for the fields above, then you can fill this field
-   7: Responsibles = “Product Owner” and “Developer“-name
-   8: Package = Here you need to fill the “Relative path to TAG” and a short overview what this TAG includes
-   9: Related Work = Please add EVERY Work item that are part of this TAG. here is an overview of the Link types you should use (Predecessor = “Bug”, “Product Backlog Item”, “Spike”), (Child = “Test Case”)
- 
- ![[Pasted image 20221101171114.png]]

3.4 These new "Work Items" can now be assigned in "Sprint Plannings" or "Twice Weeklys" to our "operation"-colleagues