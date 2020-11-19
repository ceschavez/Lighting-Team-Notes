
# Lighting Team Notes
 - 🔗 [Links](#links)
 - ✅[Feature Deployment Updated](#feature-deployment-updated)
 - [Release Templates](#release-templates)
 - 🚨[Feature Deployment Deprecated](#feature-deployment-deprecated)
 
## Links
301 Redirects
https://docs.google.com/spreadsheets/d/1yb9U0X8vBNabmNVKuTrGAUqEaiVQziqkbGNQ2FU3qVA/edit

## Feature Deployment Deprecated

> Previously, you need to have configured your Zeit account. If you don't have it, please contact David Broadlick to have access.

**CMS**
If you added or changed content on the CMS (using your local environment) you need to add it to the [staging CMS](http://mktultra.staging.wpengine.com/) by duplicating the page you affect and adding the next suffixes to the title: 
- *PAGE TITLE - WIP - USER* 
-  **Example:** Real Estate Partnerships - WIP - CESAR*

To define the URL, use the same as the title and add the suffix `-wip`:
-  **Example** `real-estate-partnerships-wip`.

This is necessary to preview the content and to not affect the living version of the page you changed, with this page added your deploy url has to have the `-wip` suffix and must be the living version of your changes.

- **Example** ecom-584-cesar-upd.real-estate.aceable.marketing/***real-estate-partnerships-wip***

**Pyramid Nuxt**
Use `yarn deploy` and follow the next instructions:
 - package: `Depends wich package you are going to deploy`
 - macro: `feature`
 - prefix: `Use your branch name`
 - env: `dev`
 - alias: `yes`

If everything goes good you will have the next message: 
`> Success! ecom-584-cesar-upd.real-estate.aceable.marketing now points to real-estate-wydoylqthb.now.sh [3s]`

The next step is to notify PM team using the first URL, in this case `ecom-584-cesar-upd.real-estate.aceable.marketing`. You need to go to your ticket and comment it with your feature URL

## Release Templates
### Ready For Release
This template is for notify DevOp when the ticket is ready to be deployed.

-   Status: Ready to be deployed ✅    
-   Feature Deployment: [https://ecom-584-cesar-dev.real-estate.aceable.marketing/real-estate-partnerships](https://ecom-584-cesar-dev.real-estate.aceable.marketing/real-estate-partnerships)
-   CMS PAGE: [http://mktultra.staging.wpengine.com/re/wp-admin/post.php?post=3958&action=edit](http://mktultra.staging.wpengine.com/re/wp-admin/post.php?post=3958&action=edit)
-   Branch: [https://github.com/aceable/pyramid/tree/ECOM-584-CESAR-DEV](https://github.com/aceable/pyramid/tree/ECOM-584-CESAR-DEV)
-   Description: This ticket is already approved [https://github.com/aceable/pyramid/pull/547](https://github.com/aceable/pyramid/pull/547) 
### Working on / Ready for QA
This template is for notify DevOp when the ticket should not be deployed.
-   Status: Not Ready to be deployed ❌    
-   Feature Deployment: [https://ecom-584-cesar-dev.real-estate.aceable.marketing/real-estate-partnerships](https://ecom-584-cesar-dev.real-estate.aceable.marketing/real-estate-partnerships)
-   WIP CMS PAGE: [http://mktultra.staging.wpengine.com/re/wp-admin/post.php?post=3958&action=edit](http://mktultra.staging.wpengine.com/re/wp-admin/post.php?post=3958&action=edit)
-   Branch: [https://github.com/aceable/pyramid/tree/ECOM-584-CESAR-DEV](https://github.com/aceable/pyramid/tree/ECOM-584-CESAR-DEV)
-   Description: This ticket is already approved [https://github.com/aceable/pyramid/pull/547](https://github.com/aceable/pyramid/pull/547) 

## Feature Deployment UPDATED

 1. Install now cli `sudo npm i -g now`
2. `yarn deploy` > feature > local
	> In case of error: Cannot read property '$t' of undefined
	> `Just comment all lines with **getAuthors** from node_modules/sheetsy/index.js`
	
3. After deploy just follow the next info:


		Finished! 🎉
    
	    We've created a tmp directory which contains the assembled build, and ran yarn install.
	        
	    Run yarn gen-local to generate static files against your local database defined in your sub project's .env.local file. This will build within the folder tmp/src/dist.
	        
	    OR
	        
	    Run yarn feature-local to generate static files against pyramid's staging wordpress database and jarvis endpoints defined in your sub project's .env.dev file. This will build within the folder tmp/src/dist.
	    
	    In order to deploy your feature local generation after build, move into your dist folder at ./tmp/src/dist and run the command 'now'.
	    
	    Use the following these selections:
	        
	    	? Set up and deploy “pyramid/tmp/src/dist”? [Y/n] y
	    	? Which scope do you want to deploy to? Aceable
	    	? Found project “aceable/dist”. Link to it? [Y/n] y
	                
	        
	    Tips:
	    	◦ Run ENV_FILE=production yarn gen-local to pull data from prod (not staging).
	    	◦ After you buid once with yarn gen-local, you can use yarn gen-local --no-build this way you're not rebuilding the JS files each time. --no-build is a nuxt generate option.
	        
	    Some debugging examples:
	    	◦ Static Server
	    		- After you generate static files via yarn gen-local, run yarn local-server which starts a server from tmp/src/dist. This uses your local mkt-ultra data.
	    	◦ Nuxt Hooks
	    		- These provide a wealth of information! Add a hook to the tmp/src/nuxt.config.js, log its parameters. Generate hooks will run after you run yarn gen-local.
	    		- More info found at https://nuxtjs.org/api/internals-generator#hooks
	    	◦ Faster file generation
	    		- Generating ALL static files takes a while for driving. Maybe comment out some of routes in the tmp/src/nuxt.config.js`.
