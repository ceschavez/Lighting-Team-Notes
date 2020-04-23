
# Lighting Team Notes

## Feature Deployment

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

 - Feature Deployment: [FD Real Estate Partnership](https://ecom-584-cesar-dev.real-estate.aceable.marketing/real-estate-partnerships)
 > Before pasting CMS page, check If you already added the data from the WIP page to the origin page (The page you used to make a copy)
 - CMS Page: [CMS Real State Partnerships](http://mktultra.staging.wpengine.com/re/wp-admin/post.php?post=3958&action=edit) 
 - Description:  In case you need to add something
### Working on / Ready for QA
This template is for notify DevOp when the ticket should not be deployed.
- `TO NOT BE DEPLOYED`
- Ticket: https://aceable.atlassian.net/browse/ECOM-584
- Feature Deployment: https://real-estate-tzcwxosqpu.now.sh/real-estate-partnerships-wip
- WIP CMS PAGE: http://mktultra.staging.wpengine.com/re/wp-admin/post.php?post=3958&action=edit
- Description: I duplicated the Driving Partnerships page to add the Real Estate Partnerships with its hubspot form, both pages have different content and maybe could change depending on PM comments, the content is already on the CMS but it is still on PM Review and maybe for the next sprint will be deployed.
