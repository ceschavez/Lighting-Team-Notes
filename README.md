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
