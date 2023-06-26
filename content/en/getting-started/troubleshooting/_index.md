---
tags: ["critical css","troubleshooting"]
title: "Troubleshooting"
type: docs
weight: 60
description: >
  If you’re having trouble using Trellis’ features, learn more about some common situations and how to troubleshoot them. 
---
## Visitors Unable to See CSS Changes

When Critical CSS is enabled, Trellis will audit the CSS files for your website. When a non-logged in user visits a page, Trellis generates a Critical CSS file and a Non-Critical CSS file. These Critical CSS files are cached, and so visitors may not immediately see any styling changes that are made until the Critical CSS files are regenerated.

{{% alert title="Note" %}}
When a WordPress user is logged in to your site, they will always see the originally coded CSS styling for your pages. Only non-logged in users are served Critical CSS.
{{% /alert %}}

### Steps to Troubleshoot

1. Log in to WordPress and see if your CSS styling is appearing on the page. Logged in users are always served the page’s original CSS files. If the styling is not appearing, you may have issues with how you’ve coded your CSS, or a different caching plugin you use might be causing the problem. Clear any other caching plugins and try again.
2. While logged in, visit the page and check the Critical CSS status in the admin bar. Trellis will tell you if it is regenerating the Critical CSS files or if there was an error during processing.

- If the status is Processing, come back to the page later to see if its status has changed to Success. You can then test the page by viewing it while not logged in. For an explanation of all Critical CSS Statuses, see [Critical CSS]({{< ref "/advanced-topics/critical-css" >}}) in Advanced Topics.
- If the status is Success but your visitors are still not seeing the CSS changes, try a hard refresh of the page or clearing your browser cache to see if the style changes appear. If the issue persists, try deleting the Critical CSS file for the page. You can do this by logging in to WordPress, visiting the page, and selecting **Manage Trellis JS/CSS Options > Purge Page CSS** in the admin bar. Once the page’s Critical CSS status is Success, log out of WordPress and visit the page again.

## Critical CSS Errors on Pages

The Critical CSS status in the admin bar shows an Error status if Trellis has difficulty parsing the page’s CSS files.

### Steps to Troubleshoot

Run your page’s CSS through a CSS validator. It could be that something in the CSS file is causing problems. You can disable a single page’s Critical CSS by calling up the page or post for editing and doing one of the following:

- If using the Block Editor, click on the Trellis icon and select **Disable Critical CSS**. Then run the page through a CSS validator.
- If using the Classic Editor, go to the Trellis panel at the bottom and select **Disable Critical CSS**. Then run the page through a CSS validator.

## REST API Error

Trellis generates Critical CSS files by connecting to the Trellis Services API hosted by Mediavine. If your Trellis instance is having trouble connecting to the Trellis Services API, you will see an error in Trellis Settings. Critical CSS will be disabled for your entire site until the Trellis Services API can be reached and can communicate with your Trellis instance.

{{% alert color="warning" title="Important" %}}
- If developing or testing with Trellis on your personal workstation (using an environment such as Local or MAMP), it is normal to see a REST API error. An SSL certificate must be present and your URL public to let your Trellis instance connect to the Trellis Services API. Test your instance in an online environment before taking it live to ensure Trellis can connect to the Trellis Services API.
- If using an online staging site or sandbox, you might also encounter REST API errors since these environments might have limited access to outside services. Check the environment’s firewall policies (explained below)  to make sure Trellis can connect to the Trellis Services API.
{{% /alert %}}

### Steps to Troubleshoot

If you are working with your site online and still see a REST API error, follow these steps:

1. Go to **Appearance > Mediavine Trellis** and click on **Advanced**. Go to the Permanent Actions section and click the **Clear** button for the Trellis Cache. It could be that something in the Trellis Cache is preventing access to the Trellis Services API.
2. Check whether you have any bot blocking or firewall plugins loaded in your WordPress installation. Plugins such as WordFence, Titan Anti-Spam, and iThemes Security have been known to cause issues connecting with the Trellis Services API.
    - **For WordFence and Titan Anti-Spam:** Set the Firewall settings to **Learning Mode**.
    - **For iThemes Security:** Make sure the REST API option is **Set to Default Access**.
3. Check with your hosting provider to see if your server has bot blocking or firewall settings enabled. If so, provide your host with the information below and ask them to add the Trellis Services API to their firewall's allowlist.

| Firewall Setting | Value |
| --- | --- |
| X-MV-Trellis-Services | trellis-services |
| User-Agent | Trellis-Services |

## Trellis Features Are Grayed Out (License Errors)

If you go to **Appearance > Mediavine Trellis** and see that some features are grayed out, it could mean that your Trellis license is not installed, you have exceeded the number of sites allowed for your license, or your license has expired.

### Steps to Troubleshoot

1. Go to **Appearance > Mediavine Trellis** and click on **License**. You can see if your license is installed or showing any errors. If you have a license entered, click the **Recheck License** button to force a validation.
2. Your Trellis license is designed to work on just one site (unless you’ve purchase a multi-site license). This means that you may run into issues if you try to add your license to both a staging site and your production site. If you’re only developing a single site, deactivate the license from your staging site, push your site to a live server, then add your license to the live site.

## Core Web Vitals Issues

When a Trellis site goes live, pages must first be visited by non-logged in users to trigger Trellis' optimizations. You can do this manually by visiting pages in Incognito mode and then checking if their Critical CSS status changes to Success. You should not test site speed until Critical CSS files are generated, as they provide a big boost. 

### Steps to Troubleshoot

1. In Incognito mode in your browser, test a post to give you a better idea of what your readers are experiencing. This is the best method for getting more accurate speed test results.
2. Check the Critical CSS status for any pages with low scores. Make sure that the Critical CSS status is Success. See [Critical CSS]({{< ref "/advanced-topics/critical-css" >}}) in Advanced Topics for more information on Critical CSS statuses.
3. For an extensive list of troubleshooting steps, see [Core Web Vitals with Trellis](https://product-help.mediavine.com/en/articles/5392546-core-web-vitals-with-trellis) in the Help Center.