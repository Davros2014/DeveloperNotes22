 
**Handover - design issues:

1. In the Brig application, as a test there are a number of layout issues that will no doubt be repeated throughout other applications. A few that were brought to our attention:
	1. Buttons - I think there are a few that need the Button_Standard class adding them, it looked they didn't have any class applied or ones that have been created in the old system and not migrated across.
	2. Icon classes in general need to be replaced - this will be a recurring theme throughout a lot of applications - also check that the person responsible for the app does a cache reset
	3. Filter groups - and filter fields need to be addressed overall
	4. Modals - general layout needs to be addressed

2. Knowit & GBGrapevine - similar issues have arisen - there will be a need for the filter groups to be redefined using grid to be responsive. 

3. There are a number of design elements that need addressing in the G109 WGS app Thanh and Mohammed are working on  here: [Thanh Trung Thai: Hi Intrexx - Design Team (David & Amir), Mohammed and I ran …](https://teams.microsoft.com/l/message/19:b590d28f9c2d4de2b825b699455602f3@thread.skype/1678360500685?tenantId=ecaa386b-c8df-4ce0-ad01-740cbdb5ba55&groupId=b428d9b4-4b81-4681-9b2a-9e7765f30e56&parentMessageId=1678353447997&teamName=Intrexx%20-%20Intranet%20Solutions&channelName=Migration&createdTime=1678360500685&allowXTenantAccess=false "https://teams.microsoft.com/l/message/19:b590d28f9c2d4de2b825b699455602f3@thread.skype/1678360500685?tenantId=ecaa386b-c8df-4ce0-ad01-740cbdb5ba55&groupId=b428d9b4-4b81-4681-9b2a-9e7765f30e56&parentMessageId=1678353447997&teamName=Intrexx%20-%20Intranet%20Solutions&channelName=Migration&createdTime=1678360500685&allowXTenantAccess=false") 
	posted in Intrexx - Intranet Solutions / Migration chat at 09 March 2023 12:15:00

4. Check fixed widths on a lot of elements that are currently set to 1440px or similar within a parent container that has a similar fixed width and so on. With padding etc this quickly pushes the layout out of the container and we have content either hidden to the screen left and/or creates a horzontal scroll in places.

5. TABMENU - some styles have been created in the globalHelpers.css file for testing purposes. These would need to be transferred to the BASF_darkblue layout in Intrexx. Also some issues with certain menu items displaying and work is needed on how the menu wraps responsively. 

6. Icons - overall they should be working well, there will be a few edge cases that might require customised css - this will be ongoing (all icons in the iconStyles.css file loaded currently in the custon_head.vm - this could of course be moved elsewhere once we refine other style sheets). I noticed the outbox icon is not showing, it should be the correct unicode, not sure why there. Could be there are other cases, something to look out for.

7. Buttons for save, delete, cancel etc need to be looked at - hover, focus and any other possible states need attention

8. Start-page - design and implementation of the introductory page of the portal

9. Language constants not fully implemented/missing in the design system - some pages are not loading properly as a result.

10. On another matter, I think the portal width seems a bit too narrow (at least on my screen). I think it has been set to 1440px and then there are further widths/margins applied to containers within that which make the actual width a percentage of that, in my case it equates to 1142.43px. Should this be changed?

