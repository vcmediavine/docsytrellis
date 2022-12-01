---
title: "Testing Your Child Theme"
linkTitle: "Testing Your Child Theme"
type: docs
date: 2022-10-04
weight: 5
description: >
  Learn best practices on how to test your Trellis child theme. 
---
As a web developer, you may already be familiar with the concept of testing your code prior to launch. When developing a child theme for Trellis, it’s especially important to not skip this step, as Trellis’ caching, optimizations, and other features make testing vital to ensure speed boosts and improvements to Core Web Vitals scores work as intended.

The WordPress Codex has an extensive list of steps you can take to make sure your child theme is functioning properly. See the [Theme Testing](https://codex.wordpress.org/Theme_Development#Theme_Testing_Process) section of the Codex for more information.

## Testing on a Staging Server

You should always test your child theme on a staging site prior to making it live. This will let you make sure things are working properly without impacting your live site.

That being said, if you’re testing your Trellis child theme on a local environment or in a sandbox with a strict firewall configuration, here are some important things to know:

- **Critical CSS requires an SSL certificate and a firewall configured to let Trellis communicate with the Trellis API.** See Troubleshooting for more information on bots and firewall issues if you receive Critical CSS errors.
- **You may experience license issues on a staging site.** Unless you’ve purchased Trellis for multiple sites, remember that a Trellis license defaults to only one WordPress installation. You can move a Trellis license from one site to another, if needed. See Troubleshooting for more information if you experience license errors.

For more information on Trellis and staging sites, see [Working With Trellis on a Staging Site](https://product-help.mediavine.com/en/articles/5964310-working-with-trellis-on-a-staging-site) in our Help Center.

## Theme Unit Testing

The WordPress Theme Unit Test Data is a special import designed to simulate a site that’s been online for several years. The import file creates a number of pages, different types of posts, several menu items, and more. Make use of this test data to ensure your child theme behaves as expected.

### Import the WordPress Theme Test

1. Download the [theme test data](https://github.com/WPTT/theme-test-data) from GitHub.
2. Go to **Tools > Import WordPress**.
3. Click **Run Importer**.

{{% alert title="Note" %}}
You may need to install the WordPress importer first. An Install link will let you install the importer before you run it.
{{% /alert %}}

4. Click **Choose File** and select the themeunittestdata.wordpress.xml file.
5. Click **Upload File and Import**.
6. Select Authors from your site for the imported data (you can choose to create new authors during import as well).
7. Select **Download and import file attachments** to make sure images and other attachments are also imported.
8. Click **Submit**.
9. Review the different pages and posts to see how the imported content renders.

## Testing Site Speed

While the other parts of this document focus on steps to take prior to launch, this part advises you to **not** do something: testing site speed.

It’s a natural thing to do when switching to a new framework that promises you increased speed and Core Web Vitals scores. But while you may be tempted to test your site’s performance ahead of time, keep these things in mind:

- If you’re using a staging site, speed tests in Google PageSpeed Insights, or other tools, may not give you accurate results.
- Trellis’ biggest impact to site speed is through the use of Critical CSS. If Critical CSS can’t connect to the Trellis API, then Critical CSS will be disabled. Also, Critical CSS files are only generated when a site visitor views a page.

When you’re ready to test your site speed, only do it twenty-four hours after you’ve activated Trellis on your live site, and test it on a page or post other than your home page. Waiting twenty-four hours will give your site time for visitors to trigger Critical CSS generation on the most-visited pages.

## What’s Next?

- Read more about Trellis Hooks
- Read more about Trellis Filters