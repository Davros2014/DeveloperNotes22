## 

Design System

This repository contains the design system components of the GTU Intranet Applications team. The components have been derived from the UI library [shadcn-vue](https://www.shadcn-vue.com/). This repo will contain only the components, `shadcn-vue` project initiation has to be done in the relevant project directory.

## 

How to add this design system into a project?

### 

Step 1 - To install shadcn-vue in a main project directory

- Install certificates according to following [DevHub](https://devhub.intranet.basf.com/documentation/setup/certificates/ca/) link
    
    **- Assuming the certificates are installed in a path `<PATH_WHERE_CACERT_PEM_FILE_EXISTS>`, open up a new **command prompt** (not powershell) and execute `set <PATH_WHERE_CACERT_PEM_FILE_EXISTS>/cacert.pem` (in case you use powershell you might run into GET request errors.)
    
    **
    
- Follow shadcn-vue installation according to [documention](https://www.shadcn-vue.com/docs/installation/nuxt.html), be mindful that you correctly installed tailwind, make sure module is added to the nuxt config. Latest running version of `shadcn-vue` is `0.10.4`. It is observed that some errors with package `color-mode` is observed for higher versions.
    
- **When you execute `npx nuxi@latest module add shadcn-nuxt` from the installation documentation, it will install the latest shadcn-nuxt module which is currently unstable. Change the version in the package.json to `0.10.4`, delete `node_modules` and `package_lock.json` execute `npm install` again.**
    
- Add the below under `extend.colors` within `tailwind.config`
    

darkBlue: {
     DEFAULT: "#004A96",
     50: "#0061C4",
     100: "#005EBF",
     200: "#0059B5",
     300: "#0054AA",
     400: "#004FA0",
     500: "#004A96",
     600: "#00458C",
     700: "#004082",
     800: "#003B77",
     900: "#00366D",
     950: "#003368",
    }

### 

Step 2 - add this repository to main project repository

Navigate to your main repository's project directory and run:

git submodule add git@gitlab.roqs.basf.net:gb-intranet-applications/design-system.git ./nuxt3/components/design_system

Edit the `.gitmodules`

[submodule "nuxt3/components/design_system"]
	path = nuxt3/components/design_system
	url = https://gitlab.roqs.basf.net/gb-intranet-applications/design-system.git # change this line
	branch = development  # Add this line

Commit the submodule

git add .gitmodules .\nuxt3\components\design_system\
git commit -m "add submodule design system"

### 

Step 3 - add the submodule to the build pipeline

To ensure your GitLab CI pipeline includes the submodule code (not just the commit hash), you’ll need to configure your pipeline to initialize and update submodules during the build process.

variables:
  GIT_SUBMODULE_STRATEGY: recursive  # add this line under variables, it initializes and updates submodules
nuxt3_compile:
  stage: compile
  image: ${CI_REGISTRY}/base-images/node:latest
  # add the before script to correctly define path with CI_JOB_TOKEN inside .gitmodules
  before_script:
    - git config --global url."https://gitlab-ci-token:${CI_JOB_TOKEN}@gitlab.roqs.basf.net".insteadOf "https://gitlab.roqs.basf.net"
    - git submodule sync --recursive

And finally (if it is not done before), set job token permission in the submodule to all groups

  

![alt text](posting-db/permissions.png)

## 

How to modify design system from the main project repository

After doing some changes

cd ./nuxt3/components/design_system
git add .                  
git commit -m "Your commit message for the submodule"
git push origin HEAD:development

Since main project repository only use the hash of the **latest** commit of the design system, we need to update that within the main project repository as well.

git add ./nuxt3/components/design_system
git commit -m "Update submodule to latest branch commit"

## 

How to clone the main project repository with the design system

Since the main project repository has the submodule, please clone it recursively. This should bring the submodule config **not the submodule code itself**. For that you need to update the submodule.

git clone --recurse-submodules git@gitlab.roqs.basf.net:gb-intranet-applications/posting-db.git

### 

Update the submodule

This refers to pulling new changes from the submodule’s remote repository. After cloning, the submodule is "locked" to the commit hash specified by the main repository. Updating the submodule means:

1. Fetching the latest changes from the submodule’s remote.
2. Moving the submodule to a newer commit (or a specific branch).

Update the submodule using

git submodule update --remote

Then commit new hash in the project directory

git add ./nuxt3/components/design_system
git commit -m "Update submodule to latest branch commit"

## 

How to remove the residual git files if you delete the submodule

`git rm --cached ./nuxt3/components/design_system`