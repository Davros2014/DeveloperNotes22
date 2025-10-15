
design issues Thanh: 

---

### **Checklist of migrated Apps on DEV (NEW Portal)**[](https://dev.azure.com/basf4ServicesCoreSystems/Intranet%20Solutions%20-%20Global%20Business%20Services/_wiki/wikis/Intranet-Solutions---Global-Business-Services.wiki/3195/Testing-migrated-APPs-as-team?anchor=**checklist-of-migrated-apps-on-dev-(new-portal)**)

#### Administration
-    User Administration 
class: FilterGroup 
-    Portal Feedback
-    Portal / App Info
-    Application Overview

#### The rest of Apps
-    PostingDB
-    WGS
-    #GBgrapevine
-    Wohnungsworkflow
-    Hub Services DB
-    Service Score @ GB
-    Application Overview
-    GIVIT
-    GBE Dashboard
-    Portal Feedback
-    Portal / App Info
-    Serviceverwaltung (CDB)
-    Basic Application
-    BRIG
-    KNOWit
 
---

### **Checklist of Migrated Apps on TEST (NEW Portal)**[](https://dev.azure.com/basf4ServicesCoreSystems/Intranet%20Solutions%20-%20Global%20Business%20Services/_wiki/wikis/Intranet-Solutions---Global-Business-Services.wiki/3195/Testing-migrated-APPs-as-team?anchor=**checklist-of-migrated-apps-on-test-(new-portal)**)

Administration
The rest of Apps

---

### **Checklist of Migrated Apps on PROD (NEW Portal)**[](https://dev.azure.com/basf4ServicesCoreSystems/Intranet%20Solutions%20-%20Global%20Business%20Services/_wiki/wikis/Intranet-Solutions---Global-Business-Services.wiki/3195/Testing-migrated-APPs-as-team?anchor=**checklist-of-migrated-apps-on-prod-(new-portal)**)

Administration
The rest of Apps 

---

##### Refined CSS

Removed hardcoded font sizes on the following styles in deprecation_support.css


``` 
[class*="Link_Icon "]::before, .Action.Icon::before, .addon-res a::before {
	/* font-size: clamp(1.6rem, 3vw, 1.8rem); */ 
	/* margin-right: 10px; */ 
	/* top: 1px; */ 
}
```


Changed padding values to reflect those as defined in the style guide ie multiples of 5px and removed fixed height

```
.FilterGroup,

.FilterGroup_Table {
  background-color: var(--darkblue5);
  /* padding: 8px 5px; */
  padding: 1rem 1rem 0 1rem;
  clear: both;
  display: flex;
  justify-content: space-between;
  /* height: 50px; */
}
```

removed padding from the bottom of the Actionbar to create a more visually balanced look in deprecationSupport.css

```
.ActionBar {
  padding: 15px 15px 0 15px;
  max-width: 1170px;
  margin: 0 0 10px 0; 
  margin-top: 0px;
  background-color: #f0f0f0;
  min-height: 50px;
  max-height: 95px;
}
```

changed margin top from -37px to -38px in the following rule to account for the gap between button and the line below -  deprecationSupport.css

```
.Container_moduleBox_Hellblau .Actions,
.ContentContainer .Actions {
  margin-top: -37px;
  height: 35px;
}
```


